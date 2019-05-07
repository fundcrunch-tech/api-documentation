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

result = requests.get(api_host)
if result.ok:
    ret = json.loads(result.text) 
```



