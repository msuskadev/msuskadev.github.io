## LUIS.ai response
```javascript
{
  "text": "Hey Bot find me a flight from WRO to JFK on 2020-11-25",
  "intents": {
    "SearchFlight": {
      "score": 0.993398368
    }
  },
  "entities": {
    "location": [
      {
        "AirportFrom": [
          "WRO"
        ],
        "$instance": {
          "AirportFrom": [
            {
              "type": "AirportFrom",
              "text": "WRO",
              "startIndex": 30,
              "endIndex": 33,
              "modelType": "Entity Extractor",
              "recognitionSources": [
                "model"
              ]
            }
          ]
        }
      },
      {
        "AirportTo": [
          "JFK"
        ],
        "$instance": {
          "AirportTo": [
            {
              "type": "AirportTo",
              "text": "JFK",
              "startIndex": 37,
              "endIndex": 40,
              "modelType": "Entity Extractor",
              "recognitionSources": [
                "model"
              ]
            }
          ]
        }
      }
    ],
    "datetime": [
      {
        "timex": [
          "2020-11-25"
        ],
        "type": "date"
      }
    ],
    "$instance": {
      "location": [
        {
          "type": "location",
          "text": "WRO",
          "startIndex": 30,
          "endIndex": 33,
          "modelType": "Entity Extractor",
          "recognitionSources": [
            "model"
          ]
        },
        {
          "type": "location",
          "text": "JFK",
          "startIndex": 37,
          "endIndex": 40,
          "modelType": "Entity Extractor",
          "recognitionSources": [
            "model"
          ]
        }
      ],
      "datetime": [
        {
          "type": "builtin.datetimeV2.date",
          "text": "2020-11-25",
          "startIndex": 44,
          "endIndex": 54,
          "modelType": "Prebuilt Entity Extractor",
          "recognitionSources": [
            "model"
          ]
        }
      ]
    }
  },
  "sentiment": {
    "label": "positive",
    "score": 0.7504654
  },
  "luisResult": {
    "query": "Hey Bot find me a flight from WRO to JFK on 2020-11-25",
    "prediction": {
      "topIntent": "SearchFlight",
      "intents": {
        "SearchFlight": {
          "score": 0.993398368
        }
      },
      "entities": {
        "location": [
          {
            "AirportFrom": [
              "WRO"
            ],
            "$instance": {
              "AirportFrom": [
                {
                  "type": "AirportFrom",
                  "text": "WRO",
                  "startIndex": 30,
                  "length": 3,
                  "modelTypeId": 1,
                  "modelType": "Entity Extractor",
                  "recognitionSources": [
                    "model"
                  ]
                }
              ]
            }
          },
          {
            "AirportTo": [
              "JFK"
            ],
            "$instance": {
              "AirportTo": [
                {
                  "type": "AirportTo",
                  "text": "JFK",
                  "startIndex": 37,
                  "length": 3,
                  "modelTypeId": 1,
                  "modelType": "Entity Extractor",
                  "recognitionSources": [
                    "model"
                  ]
                }
              ]
            }
          }
        ],
        "datetimeV2": [
          {
            "type": "date",
            "values": [
              {
                "timex": "2020-11-25",
                "resolution": [
                  {
                    "value": "2020-11-25"
                  }
                ]
              }
            ]
          }
        ],
        "$instance": {
          "location": [
            {
              "type": "location",
              "text": "WRO",
              "startIndex": 30,
              "length": 3,
              "modelTypeId": 1,
              "modelType": "Entity Extractor",
              "recognitionSources": [
                "model"
              ]
            },
            {
              "type": "location",
              "text": "JFK",
              "startIndex": 37,
              "length": 3,
              "modelTypeId": 1,
              "modelType": "Entity Extractor",
              "recognitionSources": [
                "model"
              ]
            }
          ],
          "datetimeV2": [
            {
              "type": "builtin.datetimeV2.date",
              "text": "2020-11-25",
              "startIndex": 44,
              "length": 10,
              "modelTypeId": 2,
              "modelType": "Prebuilt Entity Extractor",
              "recognitionSources": [
                "model"
              ]
            }
          ]
        }
      },
      "sentiment": {
        "label": "positive",
        "score": 0.7504654
      }
    }
  }
}
```

