---
title: usd-x.com API v1 Reference


toc_footers:
  - <a href='https://www.usd-x.com'>Back to the usd-x.com Website</a>

---

# Introduction

Version V1

Welcome to the usd-x.com API! You can use our API to access usd-x.com API endpoints, which can be used to obtain market information from our database.

Currently we are only providing a Public API which does not use authentication.

We will be releasing API V2 with full trade and coin control functionality at a later stage.

You can view API call response examples in the dark area to the right.

# General

usd-x.com offers a simple and easy to use RESTful API. All requests use the application/json content type and go over https.

All requests use the following base url:

<aside class="success">
https://www.usd-x.com/api/{version}/{method}?param=value
</aside>


# Public API

## Get Markets

> 'getmarkets' returns JSON structured like this:

```json
{
    "success": "1",
    "request": "/api/v1/public/getmarkets",
    "message": "",
    "result": [
	{

	    "MarketID": "1",
	    "MarketAssetName": "Megacoin",
	    "MarketAssetCode": "MEC",
	    "MarketAssetID": "3",
	    "MarketAssetType": "currency",
	    "BaseCurrency": "Bitcoin",
	    "BaseCurrencyCode": "BTC",
	    "BaseCurrencyID": "1",
	    "Active": true

	},
	{

	    "MarketID": "3",
	    "MarketAssetName": "Litecoin",
	    "MarketAssetCode": "LTC",
	    "MarketAssetID": "2",
	    "MarketAssetType": "currency",
	    "BaseCurrency": "Bitcoin",
	    "BaseCurrencyCode": "BTC",
	    "BaseCurrencyID": "1",
	    "Active": true

	}
    ]
}

```

This endpoint retrieves all markets.

### HTTP Request

`GET https://www.usd-x.com/api/v1/getmarkets`

## Get Market Summaries

> 'getmarketsummaries' returns JSON structured like this:

```json
{
    "success": "1",
    "request": "/api/v1/public/getmarketsummaries",
    "message": "",
    "result": [
	{
	    "MarketID": "1",
	    "LastPrice": "0.00902321",
	    "Change": "2.01",
	    "HighPrice": "0.00961681",
	    "LowPrice": "0.00853751",
	    "Volume": "3043.78746852",
	    "BTCVolume": "3043.78746852",
	    "TradeCount": "1332",
	    "BidPrice": "0.00902321",
	    "AskPrice": "0.00928729",
	    "BuyOrderCount": "7796",
	    "SellOrderCount": "7671"
	},
	{
	    "MarketID": "3",
	    "LastPrice": "0.05000000",
	    "Change": "0.00",
	    "HighPrice": "0.00000000",
	    "LowPrice": "0.00000000",
	    "Volume": "0.00000000",
	    "BTCVolume": "0.00000000",
	    "TradeCount": "0",
	    "BidPrice": "0.00000000",
	    "AskPrice": "0.02000000",
	    "BuyOrderCount": "0",
	    "SellOrderCount": "1"
	}
    ]
}

```

This endpoint retrieves summaries for all markets.

### HTTP Request

`GET https://www.usd-x.com/api/v1/getmarketsummaries`




## Get Market Summary

> 'getmarketsummary' returns JSON structured like this:

```json
{
    "success": "1",
    "request": "/api/v1/public/getmarketsummary",
    "message": "",
    "result": [
	{
	    "MarketID": "1",
	    "LastPrice": "0.00902321",
	    "Change": "2.01",
	    "HighPrice": "0.00961681",
	    "LowPrice": "0.00853751",
	    "Volume": "3043.78746852",
	    "BTCVolume": "3043.78746852",
	    "TradeCount": "1332",
	    "BidPrice": "0.00902321",
	    "AskPrice": "0.00928729",
	    "BuyOrderCount": "7796",
	    "SellOrderCount": "7671"
	}
    ]
}

```

This endpoint retrieves summary for the specified market.

### HTTP Request

`GET https://www.usd-x.com/api/v1/getmarketsummary?market_id=1`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
market_id | string | Determines which market summary data is returned, can be obtained from 'getmarkets'




## Get Order Book

> 'getorderbook' JSON return:

```json
{
    "success": "1",
    "request": "/api/v1/public/getorderbook",
    "message": "",
    "result": 
{
    "SellOrders": [
	{
	    "Type": "sell",
	    "Price": "0.00928729",
	    "OrderTime": "2016-02-12 03:43:53",
	    "Quantity": "37.04860800"
	},
	{
	    "Type": "sell",
	    "Price": "0.00943025",
	    "OrderTime": "2016-02-12 03:20:20",
	    "Quantity": "37.98811700"
	},
	{
	    "Type": "sell",
	    "Price": "0.00946113",
	    "OrderTime": "2016-02-12 03:13:08",
	    "Quantity": "61.29427500"
	}
    ],
    "BuyOrders": [
	{
	    "Type": "buy",
	    "Price": "0.00855383",
	    "OrderTime": "2016-02-12 03:35:51",
	    "Quantity": "907.10057100"
	},
	{
	    "Type": "buy",
	    "Price": "0.00853751",
	    "OrderTime": "2016-02-12 03:18:00",
	    "Quantity": "86921.80244318"
	},
	{
	    "Type": "buy",
	    "Price": "0.00853596",
	    "OrderTime": "2016-02-11 18:08:49",
	    "Quantity": "487.45194800"
	}
    ]
}

```

This endpoint retrieves the top 50 buy and sell order for the market.

### HTTP Request

`GET https://www.usd-x.com/api/v1/getorderbook?market_id=1`

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
market_id | string | Determines which market summary data is returned, can be obtained from 'getmarkets'













