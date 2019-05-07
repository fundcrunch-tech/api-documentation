# Fundcrunch API
It provides wss and REST API to access exchanges public and private data streams along with execution commands in uniform messaging format.

Supprorted exchanges: 

```
Bitmex Bittrex BitFinex Binance Bitstamp KuCoin Poloniex HitBTC Cex Coinbase Pro OKEX Huobi YOBIT
```

Data Streams:
```
Order Book, Trades, OHLC, Balances, Trade Update, Indicators
```

**Free access**

Publick market data and Indicators streams are avaliable with some limitation like delais or thresholds. No exchange accounts or private data streamse are avalebled.  

**Subscribed Users**

Subscribed users have data streams without any limitation including private data feedeing and execution functions. 

## Quick start

### Subscribe for public stream

```python
import websockets, requests
import json

api_host = 'https://fundcrunch.tech/wss'

to_subscribe = ['trade_binance_BTC_USTD', 'ohlc_binance_BTC_USDT', 'ob_binance_BTC_USDT']
to_subscribe = ",".join(to_subscribe)

url = f"{api_host}/?subscribe={to_subscribe}"
result = requests.get(url)


if result.ok:
    ret = json.loads(result.text)
    wss_url = f"{ret['source_addres']}/{ret['session']}"
    print(wss_url)
```

above code initiate wss session, subscribes to specific messages and obtain actual wss stream url like

```
wss://138.68.73.246:9443/aa11fde8-1f6d-4372-a3b7-e7eb794e3870
```




