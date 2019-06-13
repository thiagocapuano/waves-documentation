# gRPC Server

**gRPC Server** — расширение [ноды](/blockchain/node.md), которое позволяет поднимать на ноде [gRPC](https://en.wikipedia.org/wiki/GRPC)-сервисы.

gRPC-сервисы предоставляют информацию о:

* аккаунтах
* блоках
* блокчейне
* [токенах](/blockchain/token.md)
* [транзакциях](/blockchain/transaction.md)

## Генерация клиента

Для подключения к gRPC-сервисам используются клиенты, которые [генерируются](https://grpc.io/docs/tutorials/) из [.proto-файлов](https://github.com/wavesplatform/Waves/tree/master/grpc-server/src/main/protobuf).

Примеры использования gRPC-клиентов, сгенерированных из .proto-файлов:

* [Подключения к сервису транзакций на Java](https://github.com/wavesplatform/WavesJ/blob/master/examples/src/main/java/GRPCTest.java)
* [Загрузка блоков на C#](https://github.com/wavesplatform/WavesCS/blob/master/WavesCSTests/ProtobufTest.cs)
