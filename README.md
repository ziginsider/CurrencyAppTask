### Task description

Implement client Android app "currency-exchange". The main screen can be like this:
	
  <img alt="quiz app" src="/img/demo.gif" width="250" height="500" />

1) `User` can see a list of currencies on the main page.
2) Each item of the list should consist from icon of the currency, base name of the currency, description and rate (current currency base price). Let's use 5 decimal places precision for rate value. For example, see demo above.
3) Rates of currencies are refreshed every 5 seconds.
4) `User` can tap on the rate field of any item, then:
    - Choosen item is moved to the top of currencies list
    - `User` can enter currency value in this rate field
    - Other currency rates is recalculated according to entered currency value and base rate value of every currency item. So, there is a currency exchange implementation. 

  <img alt="set value" src="/img/demo2.gif" width="250" height="500" />

5) `User` can tap on any currency item to move on detailed currency screen. This screen consist the same info as the currency item plus the last currency update date (in any human readable format, e.g. *2022-09-30 01:16:06*). The currency rate is also refreshed.
 
### Acceptance criteria

0) Use *Kotlin*

1) Implement list of currencies using *RecyclerView*. 

    Available currency bases: **USD, EUR, CHF, HRK, MXN, ZAR, CNY, THB, AUD, ILS, KRW, JPY, PLN, GBP, IDR, HUF, PHP, TRY, RUB, HKD, ISK, DKK, ADA, CAD, MYR, BGN, NOK, RON, SGD, CZK, SEK, NZD, BRL, INR**

    You can find icons of currencies in this repo.

    Description for each currency see [here](strings.xml)


2) Use REST API via *Retrofit* to obtain currency data

    To get data of **all** currencies use:

      ```https://us-central1-epam-laba-13-1527598553135.cloudfunctions.net/myWebsiteBackend/api/currency/```

    To get currency data of specific **base** use: 

      ```https://us-central1-epam-laba-13-1527598553135.cloudfunctions.net/myWebsiteBackend/api/currency/{base}```

    For example, request ```https://us-central1-epam-laba-13-1527598553135.cloudfunctions.net/myWebsiteBackend/api/currency/USD``` 

    returns JSON-file kind of ```{"date":1659706268,"rate":0.032063693827542705,"base":"USD"}``` 

    where **date** - is the epoch time in ms for request moment, **rate** - current rate of the currency.

3) Use *Dagger* as Dependency Injection library for this app. It can be useful to get instance of Retrofit, OkHttpClient, lib for JSON parsing, etc. Using *Hilt* is up to you.

4) Use *MVVM* and *VM* to keep currencies states and getting request to server.

5) Use *Coroutines* and *Flow* to work with server requests and responses.  

