## LUIS.ai response
```javascript
{
  "text": "I need two tickets from London to Sydney on Christmas Eve this year",
  "intents": {
    "SearchFlight": {
      "score": 0.9057049
    }
  },
  "entities": {
    "location": [
      {
        "CityFrom": [
          "London"
        ],
        "$instance": {
          "CityFrom": [
            {
              "type": "CityFrom",
              "text": "London",
              "startIndex": 24,
              "endIndex": 30,
              "modelType": "Entity Extractor",
              "recognitionSources": [
                "model"
              ]
            }
          ]
        }
      },
      {
        "CityTo": [
          "Sydney"
        ],
        "$instance": {
          "CityTo": [
            {
              "type": "CityTo",
              "text": "Sydney",
              "startIndex": 34,
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
    "geographyV2": [
      {
        "location": "London",
        "type": "city"
      },
      {
        "location": "Sydney",
        "type": "city"
      }
    ],
    "datetime": [
      {
        "timex": [
          "2020-12-24"
        ],
        "type": "date"
      }
    ],
    "$instance": {
      "location": [
        {
          "type": "location",
          "text": "London",
          "startIndex": 24,
          "endIndex": 30,
          "modelType": "Entity Extractor",
          "recognitionSources": [
            "model"
          ]
        },
        {
          "type": "location",
          "text": "Sydney",
          "startIndex": 34,
          "endIndex": 40,
          "modelType": "Entity Extractor",
          "recognitionSources": [
            "model"
          ]
        }
      ],
      "geographyV2": [
        {
          "type": "builtin.geographyV2.city",
          "text": "London",
          "startIndex": 24,
          "endIndex": 30,
          "modelType": "Prebuilt Entity Extractor",
          "recognitionSources": [
            "model"
          ]
        },
        {
          "type": "builtin.geographyV2.city",
          "text": "Sydney",
          "startIndex": 34,
          "endIndex": 40,
          "modelType": "Prebuilt Entity Extractor",
          "recognitionSources": [
            "model"
          ]
        }
      ],
      "datetime": [
        {
          "type": "builtin.datetimeV2.date",
          "text": "Christmas Eve this year",
          "startIndex": 44,
          "endIndex": 67,
          "modelType": "Prebuilt Entity Extractor",
          "recognitionSources": [
            "model"
          ]
        }
      ]
    }
  },
  "sentiment": {
    "label": "neutral",
    "score": 0.5
  },
  "luisResult": {
    "query": "I need two tickets from London to Sydney on Christmas Eve this year",
    "prediction": {
      "topIntent": "SearchFlight",
      "intents": {
        "SearchFlight": {
          "score": 0.9057049
        }
      },
      "entities": {
        "location": [
          {
            "CityFrom": [
              "London"
            ],
            "$instance": {
              "CityFrom": [
                {
                  "type": "CityFrom",
                  "text": "London",
                  "startIndex": 24,
                  "length": 6,
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
            "CityTo": [
              "Sydney"
            ],
            "$instance": {
              "CityTo": [
                {
                  "type": "CityTo",
                  "text": "Sydney",
                  "startIndex": 34,
                  "length": 6,
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
        "geographyV2": [
          {
            "value": "London",
            "type": "city"
          },
          {
            "value": "Sydney",
            "type": "city"
          }
        ],
        "datetimeV2": [
          {
            "type": "date",
            "values": [
              {
                "timex": "2020-12-24",
                "resolution": [
                  {
                    "value": "2020-12-24"
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
              "text": "London",
              "startIndex": 24,
              "length": 6,
              "modelTypeId": 1,
              "modelType": "Entity Extractor",
              "recognitionSources": [
                "model"
              ]
            },
            {
              "type": "location",
              "text": "Sydney",
              "startIndex": 34,
              "length": 6,
              "modelTypeId": 1,
              "modelType": "Entity Extractor",
              "recognitionSources": [
                "model"
              ]
            }
          ],
          "geographyV2": [
            {
              "type": "builtin.geographyV2.city",
              "text": "London",
              "startIndex": 24,
              "length": 6,
              "modelTypeId": 2,
              "modelType": "Prebuilt Entity Extractor",
              "recognitionSources": [
                "model"
              ]
            },
            {
              "type": "builtin.geographyV2.city",
              "text": "Sydney",
              "startIndex": 34,
              "length": 6,
              "modelTypeId": 2,
              "modelType": "Prebuilt Entity Extractor",
              "recognitionSources": [
                "model"
              ]
            }
          ],
          "datetimeV2": [
            {
              "type": "builtin.datetimeV2.date",
              "text": "Christmas Eve this year",
              "startIndex": 44,
              "length": 23,
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
        "label": "neutral",
        "score": 0.5
      }
    }
  }
}
```

