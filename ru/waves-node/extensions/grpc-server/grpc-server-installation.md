# Установка gRPC Server

Расширение [gRPC Server](/waves-node/extensions/grpc-server.md) можно установить на [ноду](/blockchain/node.md) двумя способами: с помощью deb-пакета и с помощью zip-файла.

## Установка с помощью deb-пакета

1. Скачайте deb-пакет из раздела [Releases](https://github.com/wavesplatform/Waves/releases) на Github. Для мейннета это файл grpc-server\_{номер версии}\_all.deb, для тестнета — grpc-server-testnet\_{номер версии}\_all.deb.

2. Установите пакет с помощью команды:

``` console
sudo dpkg -i grpc-server_{номер версии}_all.deb
```

3. В файл конфигурации добавьте следующую строчку:

```
waves.extensions += com.wavesplatform.api.grpc.GRPCServerExtension
```

Для мейннета файл конфигурации находится по адресу /etc/waves/waves.conf, для тестнета — /etc/waves-testnet/waves.conf.

4. Перезапустите ноду.

Если нода запущена в мейннете, выполните команду:

``` console
sudo systemctl restart waves
```

Если нода запущена в тестнете, выполните команду:

``` console
sudo systemctl restart waves-testnet
```

## Установка с помощью zip-файла

1. Скачайте zip-файл grpc-server-{номер версии}.zip из раздела [Releases](https://github.com/wavesplatform/Waves/releases) на Github.

2. Распакуйте архив в директорию с JAR-файлом ноды.

3. Создайте новый файл конфигурации или откройте существующий и добавьте в него строчку:

```
waves.extensions += com.wavesplatform.api.grpc.GRPCServerExtension
```

4. Выполните команду:

```
java -cp 'waves-all-1.0.0.jar:grpc-server-1.0.0/lib/*' com.wavesplatform.Application {название файла конфигурации}.conf
```
