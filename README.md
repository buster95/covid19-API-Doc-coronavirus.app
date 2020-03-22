# COVID-19-API

API Service for tracking the COVID-19

> All endpoints are from [coronavirus.app](https://coronavirus.app)

## API Document

### **Root**
> https://coronavirus.app/


### **Endpoints**


> **Checkpoint Count by Day**

Request
<a href="https://coronavirus.app/get-checkpoints" target="_BLANK"><img src="https://www.iconfinder.com/icons/3049251/download/svg/512" style="display:inline;width:48px;margin-bottom:-20px;"/></a>

```json
GET /get-checkpoints
```
Successful Response:
```json
HTTP/1.1 200 OK
Content-Type: application/json

{
    "data": [
        {
            "id": "20200322",
            "createdAt": "2020-03-22T18:42:46.284Z",
            "infected": 330355,
            "dead": 14446,
            "recovered": 95236,
            "hide": false,
            "sick": 220673
        },
        {
            "hide": false,
            "infected": 305404,
            "recovered": 93138,
            "sick": 199263,
            "dead": 13003,
            "id": "20200321",
            "createdAt": "2020-03-21T23:55:06.119Z"
        },
        {
            "hide": false,
            "infected": 273014,
            "recovered": 89211,
            "sick": 172453,
            "dead": 11350,
            "id": "20200320",
            "createdAt": "2020-03-20T23:55:08.486Z"
        }
    ]
}
```


> **Places Count by Country**

Request
<a href="https://coronavirus.app/get-places" target="_BLANK"><img src="https://www.iconfinder.com/icons/3049251/download/svg/512" style="display:inline;width:48px;margin-bottom:-20px;"/></a>

```json
GET /get-places
```
Successful Response:
```json
HTTP/1.1 200 OK
Content-Type: application/json

{
    "data": [
        {
            "dead": 0,
            "lastUpdated": "2020-03-22T18:28:04.447Z",
            "id": "9Y5wmCqNCC6ZrenM31uA",
            "infected": 2,
            "recovered": 0,
            "latitude": 12.136389,
            "longitude": -86.251389,
            "name": "Nicaragua",
            "country": "NI",
            "sick": 2
        },
        {
            "infected": 2,
            "recovered": 0,
            "latitude": 20.9517,
            "longitude": 85.0985,
            "name": "Odisha",
            "country": "IN",
            "dead": 0,
            "lastUpdated": "2020-03-22T18:26:02.786Z",
            "id": "0VG7S6aaK4eSo59fL9JO",
            "sick": 2
        }
    ]
}
```


> **History Count by Country and Day**

Request
<a href="https://coronavirus.app/get-history?id=9Y5wmCqNCC6ZrenM31uA" target="_BLANK"><img src="https://www.iconfinder.com/icons/3049251/download/svg/512" style="display:inline;width:48px;margin-bottom:-20px;"/></a>

```json
GET /get-history?id=[country_id]
GET /get-history?id=9Y5wmCqNCC6ZrenM31uA
```
Successful Response:
```json
HTTP/1.1 200 OK
Content-Type: application/json

{
    "data": {
        "id": "9Y5wmCqNCC6ZrenM31uA",
        "history": [
            {
                "day": "20200322",
                "infected": 2,
                "dead": 0,
                "recovered": 0,
                "sick": 2
            },
            {
                "day": "20200321",
                "infected": 2,
                "dead": 0,
                "recovered": 0,
                "sick": 2
            },
            {
                "day": "20200320",
                "infected": 2,
                "dead": 0,
                "recovered": 0,
                "sick": 2
            },
            {
                "day": "20200319",
                "infected": 1,
                "dead": 0,
                "recovered": 0,
                "sick": 1
            }
        ],
        "latitude": 12.136389,
        "longitude": -86.251389,
        "country": "NI",
        "name": "Nicaragua",
        "lastUpdated": "2020-03-22T18:58:03.547Z"
    }
}
```


> **Get Country Flags**

Request
<a href="https://coronavirus.app/assets/img/flags/NI.svg" target="_BLANK"><img src="https://www.iconfinder.com/icons/3049251/download/svg/512" style="display:inline;width:48px;margin-bottom:-20px;"/></a>

```json
GET /assets/img/flags/[country].svg
GET /assets/img/flags/NI.svg
```

Successful Response:
[![Country Flags](https://coronavirus.app/assets/img/flags/NI.svg)](https://coronavirus.app/assets/img/flags/NI.svg)

## License
This project is released under the [MIT License](http://opensource.org/licenses/MIT). See LICENSE for details.