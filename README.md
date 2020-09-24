# Go API client for Financial Modeling Prep (fmpcloud.io)

![GitHub release (latest by date)](https://img.shields.io/github/v/release/spacecodewor/fmpcloud-go) ![GitHub](https://img.shields.io/github/license/spacecodewor/fmpcloud-go) ![GitHub go.mod Go version](https://img.shields.io/github/go-mod/go-version/spacecodewor/fmpcloud-go) [![Go Report Card](https://goreportcard.com/badge/github.com/spacecodewor/fmpcloud-go)](https://goreportcard.com/report/github.com/spacecodewor/fmpcloud-go)

## Overview
- API documentation [FmpCloud](https://fmpcloud.io/documentation) or [Financial Modeling Prep](https://financialmodelingprep.com/developer/docs/)
- API version: 3
- Package version: 1.0.4

## Support Methods 
* Company Valuation
* Calendars
* Institutional Fund
* International Filings
* Stock Time Series
* Market Indexes
* Commodities
* ETF
* Mutual Funds
* EuroNext
* TSX
* Stock Market
* Cryptocurrencies
* Forex (FX)
* Technical Indicators
* Analyst Estimates


## Installation
```sh
go get -u github.com/spacecodewor/fmpcloud-go
```

Example:

```go
APIClient, err := NewAPIClient(Config{
    APIKey: "YOU_KEY",
    Debug:  true,
    Timeout: 5,
})

if err != nil {
    log.Println("Error init api client: " + err.Error())
}

// Get rating by symbol
rating, err := APIClient.CompanyValuation.Rating("AAPL")
if err != nil {
    log.Println("Error get rating: " + err.Error())
}

// Get Company profile by symbol
profile, err := APIClient.Stock.CompanyProfile("AAPL")
if err != nil {
    log.Println("Error get company profile: " + err.Error())
}

// Get real-time single quote
quote, err := APIClient.Stock.Quote("AAPL")
if err != nil {
    log.Println("Error get quote: " + err.Error())
}

// Crypto avalible simbol list
cList, err := APIClient.Crypto.AvalibleSymbols()
if err != nil {
    log.Println("Error get crypto symbols list: " + err.Error())
}

// Crypto quotes list
cQuotes, err := APIClient.Crypto.Quotes()
if err != nil {
    log.Println("Error get crypto quotes: " + err.Error())
}

fList, err := APIClient.Forex.AvalibleSymbols()
if err != nil {
    log.Println("Error get forex symbols list: " + err.Error())
}
    
fQuotes, err := APIClient.Forex.Quotes()
if err != nil {
    log.Println("Error get forex quotes: " + err.Error())
}
```

## License
[Apache](https://github.com/spacecodewor/fmpcloud-go/blob/master/LICENSE)