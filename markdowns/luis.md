## How does LUIS.ai work?


### _Question: "Book me a flight to Paris"_


```javascript
{
    "query": "Book me a flight to Paris",
    "prediction": {
        "topIntent": "BookFlight",
        "intents": {
            "BookFlight": {
                "score": 0.9887482
            },
            "None": {
                "score": 0.04272597
            },
            "LocationFinder": {
                "score": 0.0125702191
            },
            "Reminder": {
                "score": 0.00375502417
            },
            "FoodOrder": {
                "score": 3.765154e-7
            }
        },
        "entities": {
            "Location": [
                "Paris"
            ]
        }
    }
}
```

