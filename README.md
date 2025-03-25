# gocurrency

[![Go Report Card](https://goreportcard.com/badge/ae0000/gocurrency)](https://goreportcard.com/report/ae0000/gocurrency)
[![Build Status](https://travis-ci.org/ae0000/gocurrency.svg?branch=master)](https://travis-ci.org/ae0000/gocurrency)
[![cover.run](https://cover.run/go/github.com/ae0000/gocurrency.svg?style=flat&tag=golang-1.10)](https://cover.run/go?tag=golang-1.10&repo=github.com%2Fae0000%2Fgocurrency)
[![GoDoc](https://godoc.org/github.com/ae0000/gocurrency?status.svg)](https://godoc.org/github.com/ae0000/gocurrency)
[![License](https://img.shields.io/dub/l/vibe-d.svg)](https://github.com/ae0000/gocurrency/blob/master/LICENSE)

gocurrency provides an easy way to get country data. See below for usage. Each country consists of the following struct:

```
Country{
    Code:           "AU", // iso2 code
    Currency:       "AUD",
    CurrencySymbol: "$",
    Phone:          "+61",
    Name:           "Australia",
    NameZH:         "对应的中文",
},
```

## Install

```
go get -u github.com/gwsee/gocurrency
```

## Usage

#### Get a list of countries (to iterate over, etc.)

```
for _, c := range gocurrency.Countries {
    fmt.Println(c.Name, c.Code, c.Currency)
}
```

#### Get a countries phone, name, currency symbol or currency

```
countryCode := "AU"
fmt.Printf("In %s where the phone ext is %s, the price is: %s10.00 (%s)",
    gocurrency.Name(countryCode),
    gocurrency.Phone(countryCode),
    gocurrency.CurrencySymbol(countryCode),
    gocurrency.Currency(countryCode))

// In Australia where the phone ext is +61, the price is: $10.00 (AUD)
```

#### Get a country

```
c := gocurrency.GetCountry(users.CountryCode)
fmt.Println(c.Name)
fmt.Println(c.Phone)
fmt.Println(c.Currency)
```

#### Get a list of names

```
names := gocurrency.CountryNames()
for _, c := range names{
    fmt.Println(c)
}
```

#### Get a list of codes

```
codes := gocurrency.CountryCodes()
for _, c := range codes{
    fmt.Println(c)
}
```
