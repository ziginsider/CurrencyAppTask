### Description

Implement client Android app "list of currencies". The main screen can be like this:
	
  <img alt="quiz app" src="/img/demo.gif" width="250" height="500" />

- `User` can see a list of currencies of the main page.
- Each item of the list should consist from icon of the currency, base name of the currency, description and rate (current currency price). For example, see demo above.
- Rates of currencies are refreshed every 5 seconds.
- `User` can tap on any currency item to move on detailed currency screen. This screen consist the same info as currency item plus the last currency update data. 
 
### Acceptance criteria

0) Use Kotlin

1) Implement list of currencies using *RecyclerView*. 

Available currency bases: USD, EUR, CHF, HRK, MXN, ZAR, CNY, THB, AUD, ILS, KRW, JPY, PLN, GBP, IDR, HUF, PHP, TRY, RUB, HKD, ISK, DKK, ADA, CAD, MYR, BGN, NOK, RON, SGD, CZK, SEK, NZD, BRL, INR

You can find icons of currencies in this repo.

Description for each currency see [here](strings)


2) Use REST API via *Retrofit* to obtain currency data

To get data of all currencies use:

 ```https://us-central1-epam-laba-13-1527598553135.cloudfunctions.net/myWebsiteBackend/api/currency/```

  To get currency data of specific base use: 

 ```https://us-central1-epam-laba-13-1527598553135.cloudfunctions.net/myWebsiteBackend/api/currency/{base}```

For example, request ```https://us-central1-epam-laba-13-1527598553135.cloudfunctions.net/myWebsiteBackend/api/currency/USD``` 
returns JSON-file kind of 
```{"date":1659706268,"rate":0.032063693827542705,"base":"USD"}``` 
date - is the epoch request time in ms, rate - current rate of the currency.


3) Use *Dagger* as Dependency Injection library for this app. It can be useful to get instance of Retrofit, OkHttpClient, lib for JSON parsing, etc. Using *Hilt* is up to you.

4) Use MVVM and VM to keep currencies states and getting request to server.

5) Use *Coroutines* and *Flow* to work with server requests and responses  

