#Smart Contracts Tools

There are bunch of tools for developers in Waves ecosystem.

## Code
You have two main options to write code with syntax highlighting and IntelliSense (code completion):
 - [Online IDE](https://ide.wavesplatform.com)
 - [Visual Studio Code Extension](../developer-tools/waves-ide.md)

>[!TIP]
> Online IDE and Visual Studio Code Extension support helper functions in REPL-like consoles.
> [Read more]() to find out more details about supported functions.

## Compiling and decompiling scripts
RIDE compiler is a part of [Waves Node](https://github.com/wavesplatform/Waves) and available in API. For example, you can find documentation for Waves public nodes by the following link: [https://nodes.wavesplatform.com/api-docs/index.html#!/utils/compile](https://nodes.wavesplatform.com/api-docs/index.html#!/utils/compile).
If you want to compile scripts without a node you can use [ride-js](https://github.com/wavesplatform/ride-js) library or use [Maven Compiler](../ride-language/maven-compiler.md)

>[!NOTE]
> To decompile script please use [/utils/decompile](https://nodes.wavesplatform.com/api-docs/index.html#!/utils/decompile_1) method.

## Testing
You can use [Waves IDE Console]() to send transactions and test your contract. We highly recommend to read more about console function in the [overview](../waves-console-commands/waves-console-commands.md) and [examples](../waves-console-commands/examples.md) sections of documentation.