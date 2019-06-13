# Trading bot

Our trading bot will use a [scalping strategy](https://www.investopedia.com/articles/trading/05/scalping.asp) — every 15 seconds it's going to buy assets at a mean price minus some price step and then sell them at a mean price plus some step. Generally, it's not recommended to use scalping strategy, but we choose it for simplicity.

In this tutorial, we use Python and [PyWaves](https://pypi.org/project/PyWaves/) package. Check out [Client libraries](https://docs.wavesplatform.com/en/waves-api-and-sdk/client-libraries.html) page to get the library for your language.

## Running the bot

Install [PyWaves](https://pypi.org/project/PyWaves/) package. PyWaves is a wrapper around [Waves Node REST API](https://nodes.wavesnodes.com/api-docs/index.html).

``` console
pip install pywaves
```

Install [configparser](https://pypi.org/project/configparser/) package.

``` console
pip install configparser
```

Clone [demo-python-trading-bot](https://github.com/wavesplatform/demo-python-trading-bot.git) repository.

``` console
git clone https://github.com/wavesplatform/demo-python-trading-bot.git
```

Make changes in the [config.cfg](https://github.com/wavesplatform/demo-python-trading-bot/blob/master/config.cfg) file and run the program.

``` console
cd demo-python-trading-bot
python SimpleBot.py
```
