🤖 Cashmere Bot
===============

## Description

Cashmere is a crypto trading bot that uses [TradingView](https://www.tradingview.com) alerts to process orders. Using your TradingView strategies you can send alerts via email, Cashmere will then parse your email message and place an order on yout behalf.

Cashmere uses a distributed database back-end as its configuration store. All user data is encrypted in transit using TLS 1.2 and at rest, using AES in counter mode. Upon first run of the application, you will be given a user GUID, which you need to keep safe. This will identify you on the system and allow you to restore your configuration at any time.

## Install

**macOS**

Cashmere is available via [Homebrew](https://formulae.brew.sh/formula/cashmere) for macOS:

```sh
brew install cashmere

```

Run

```sh
cashmere
```

**Windows**

Cashmere is available via [Chocolatey](https://chocolatey.org/packages/cashmere):

```sh
choco install cashmere
```

Run

```sh
cashmere
```
  
## Exchanges

The following is a list of exchanges that Cashmere supports and a list of exchanges that TradingView supports. It's our endeavour to have Cashmere in parity with the exchanges it supports.

Supported exchanges:

* BitMEX
* Binance

TradingView unsupported exchanges:

* Coinbase
* Bitfinex
* Bittrex
* Kraken
* Poliniex
* Huobi
* HitBTC
* Bitstamp
* bitFlyer
* Mercado
* BX.in.th
* CEX.IO
* Bitso
* BTCYou
* OKcoin
* Coinfloor

## Alert Format

Cashmere needs the TradingView alerts to be in a specific format for it to place trades on your behalf. The below templates outlines the values that are need:

**Buy Order**

```sh
##CASHMERE
##USER:33DBB350-0BB8-2EA5-8902-E17EA59FAD51
##STRATEGYNAME:HA-ICHIMOKU-BREAKOUT-4H
##EXCHANGE:BINANCE
##ACTION:ENTER-LONG
##ORDERTYPE:MARKET
##PAIR:BTC-USDT
##AMOUNT:1000-USDT
```

**Sell Order**

```sh
##CASHMERE
##USER:33DBB350-0BB8-2EA5-8902-E17EA59FAD51
##STRATEGYNAME:HA-ICHIMOKU-BREAKOUT-4H
##EXCHANGE:BINANCE
##ACTION:CLOSE-LONG
##ORDERTYPE:MARKET
##PAIR:MATIC-USDT
##AMOUNT:ALL
```

**Fields**

* CASHMERE - Leae as is
* USER - Your GUID e.g. 33DBB350-0BB8-2EA5-8902-E17EA59FAD51
* STRATEGYNAME - A description of your stretgy for the bot's UI e.g. HA-ICHIMOKU-BREAKOUT-4H
* EXCHANGE - The exchange to place the order on. Supported values are Binance, BitMEX
* ACTION - Order action to perform. Supported values are Enter-Long, Close-Long, Enter-Short, Close-Short
* ORDERTYPE - The type of order for the action. Market is the only supported type for now
* PAIR - The asset pair you will be placing an order on e.g BTC-USDT
* AMOUNT - The amount of an asset to buy/sell. Supported values are numbers. Also ALL, when closing an order.
