# Flutter Bitkub Exchange 

Flutter Bitkub Exchange is a Flutter's library for calling API of the [https://www.bitkub.com/](https://www.bitkub.com/)

## Installation
Add dependencies in pubspec.yaml

```bash
flutter_bitkub_exchange: 1.0.0
```

## Usage

Import the package to your project.

```dart
import 'package:flutter_bitkub_exchange/bitkub_exchange.dart';
```

## Using Public API

Create instance without API Key. 

```dart
var bk = BitkubExchangeService();
```


### Market Data (Ticker)

Get ticker information such as last price, high in 24Hr , volume. 

```dart
  var ticker = await bk.fetchMarketTicker(currency: "THB_BTC");
  for(var currency in ticker.list){
    // currency.id;
    // currency.pairName;
    // currency.last;
    // currency.lowestAsk;
    // currency.highestBid;
    // currency.percentChange;
    // currency.baseVolume;
    // currency.quoteVolume;
    // currency.high24hr;
    // currency.lowestAsk;
  }
```

### Get Server Timestamp

Get server timestamp in seconds (Epoch Unix).

```dart
  var server = await bk.fetchServerTime();
  // server.serverTime;
  }
```


### Get Available Pair-Currency 

Get List all available symbols.

```dart
  var data = await bk.fetchMarketSymbols();
  for(var currency in data.items){
    // currency.id;
    // currency.symbol;
    // currency.info
  }
```



