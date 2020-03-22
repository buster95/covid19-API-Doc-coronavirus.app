# COVID-19-API

API Service for tracking the COVID-19

> Based on [coronavirus.app](https://coronavirus.app)

## Try it
[![Run on Ainize](https://ainize.ai/static/images/run_on_ainize_button.svg)](https://ainize.web.app/redirect?git_repo=github.com/Laeyoung/Wuhan-Coronavirus-API)

## API Document

### Endpoints
**Root**
> https://coronavirus.app/


**Gets Checkpoints Count by Date:**
```json
GET /get-checkpoints
```


https://coronavirus.app/get-places

https://coronavirus.app/get-history?id=vkkXVaqUswO5JsMZx0mX

### Brief


**Successful Response:**
```json
HTTP/1.1 200 OK
Content-Type: application/json

{
	"confirmed": 7783,
	"deaths": 170,
	"recovered": 133
}
```

**Curl:**
```sh
curl -X GET "https://wuhan-coronavirus-api.laeyoung.endpoint.ainize.ai/jhu-edu/brief" -H "accept: application/json"
```

**Browser:**
https://wuhan-coronavirus-api.laeyoung.endpoint.ainize.ai/jhu-edu/brief

### Latest

**Request:**
```json
GET /jhu-edu/latest
```

Options
- Filter by country's iso2 or iso3 code
```json
GET /jhu-edu/latest?iso2=US
```
- Make the sum of all the cities or the states in those countries
```json
GET /jhu-edu/latest?onlyCountries=true
```
You can uses both options together.

**Successful Response:**
```json
HTTP/1.1 200 OK
Content-Type: application/json

[
  {
    "provincestate": "Anhui",
    "countryregion": "Mainland China",
    "lastupdate": "2020-02-29T07:21:21.001Z",
    "confirmed": 990,
    "deaths": 6,
    "recovered": 821,
    "location": {
      "lat": 31.8257,
      "lng": 117.2264
    },
    "countrycode": {
      "iso2": "CN",
      "iso3": "CHN"
    }
  }, {
    "provincestate": "Beijing",
    "countryregion": "Mainland China",
    "lastupdate": "2020-02-29T07:21:21.001Z",
    "confirmed": 410,
    "deaths": 7,
    "recovered": 257,
    "location": {
      "lat": 40.1824,
      "lng": 116.4142
    },
    "countrycode": {
      "iso2": "CN",
      "iso3": "CHN"
    }
  }, ...
]
```

**Curl:**
```sh
curl -X GET "https://wuhan-coronavirus-api.laeyoung.endpoint.ainize.ai/jhu-edu/latest" -H "accept: application/json"
```

**Browser:**
- https://wuhan-coronavirus-api.laeyoung.endpoint.ainize.ai/jhu-edu/latest
- https://wuhan-coronavirus-api.laeyoung.endpoint.ainize.ai/jhu-edu/latest?iso2=US&onlyCountries=true


### Timeseries

**Request:**
```json
GET /jhu-edu/timeseries
```

Options
- Filter by country's iso2 or iso3 code
```json
GET /jhu-edu/timeseries?iso2=US
```
- Make the sum of all the cities or the states in those countries
```json
GET /jhu-edu/timeseries?onlyCountries=true
```
You can uses both options together.

**Successful Response:**
```json
HTTP/1.1 200 OK
Content-Type: application/json

[
  {
    "provincestate": "Anhui",
    "countryregion": "Mainland China",
    "lastupdate": "2020-02-29T08:15:03.208Z",
    "location": {
      "lat": 31.8257,
      "lng": 117.2264
    },
    "countrycode": {
      "iso2": "CN",
      "iso3": "CHN"
    },
    "timeseries": {
      "1/22/20": {
        "confirmed": 1,
        "deaths": 0,
        "recovered": 0
      },
      "1/23/20": {
        "confirmed": 9,
        "deaths": 0,
        "recovered": 0
      }, ...
    }
  }, {
    "provincestate": "Beijing",
    "countryregion": "Mainland China",
    "lastupdate": "2020-02-29T08:15:03.208Z",
    "location": {
      "lat": 40.1824,
      "lng": 116.4142
    },
    "countrycode": {
      "iso2": "CN",
      "iso3": "CHN"
    },    
    "timeseries": {
      "1/22/20": {
        "confirmed": 14,
        "deaths": 0,
        "recovered": 0
      },
      "1/23/20": {
        "confirmed": 22,
        "deaths": 0,
        "recovered": 0
      }, ...
    }
  }, ...
]
```

**Curl:**
```sh
curl -X GET "https://wuhan-coronavirus-api.laeyoung.endpoint.ainize.ai/jhu-edu/timeseries" -H "accept: application/json"
```

**Browser:**
- https://wuhan-coronavirus-api.laeyoung.endpoint.ainize.ai/jhu-edu/timeseries
- https://wuhan-coronavirus-api.laeyoung.endpoint.ainize.ai/jhu-edu/timeseries?iso2=US&onlyCountries=true

### Services using COVID-19-API
- https://corona-board.soaple.endpoint.ainize.ai/
- https://wordpress.org/plugins/corona-virus-data/ (WordPress plugin)
- https://corona-three.now.sh/

### Original data source
[Novel Coronavirus (COVID-19) Cases](https://github.com/CSSEGISandData/COVID-19), provided by JHU CSSE

## License
This project is released under the [MIT License](http://opensource.org/licenses/MIT). See LICENSE for details.

## Terms of Use
You can uses this Repo and API service freely, even commercial uses. But this term of use rely on data sources. You have to check each terms of use of data sources ([JHU CSSE](https://github.com/CSSEGISandData/COVID-19/blob/master/README.md), [livecod(kor)](https://github.com/LiveCoronaDetector/livecod/blob/master/README.md)).