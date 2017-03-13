### WeatherObserved

This entity contains a harmonised description of the weather at a particular location and time. This entity is primarily associated with the vertical segments of the environment and agriculture but is applicable to many different applications.

&lt;WeatherObserved&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                             | Mandatory/ Optional | May be Null |
|----------------|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                              | M                  | N           |
| type           | Text           | Must be equal to "**WeatherObserved**".                                                                                                                                                                                                 | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                              | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                       | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                 | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                           | M                  | Y           |
| schemaVersion  | Text           | Indicates the version number of the data entity via a sequence of characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. | O                  | Y           |

&lt;Weather Observed&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name      | Attribute Type                 | Description                                                                                                                                                                                                                                                               | Mandatory/ Optional | May be Null |
|---------------------|--------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| location            | geo:json                       | The geo:json encoded map location (point or polygon), of this weather observation.                                                                                                                                                                                        | M                  | N           |
| refDevice           | List of Reference              | Reference to the unique ids of the device(s) which captured this weather observation.                                                                                                                                                                                     | O                  | Y           |
| dateObserved        | DateTime                       | The date and time of this weather observation in ISO8601 UTCformat.                                                                                                                                                                                                       | M                  | N           |
| weatherType         | Text                           | The weather type. A choice from an enumerated list. One of:                                                                                                                                                                                                               <br><br>**notAvailable, clearNight, sunnyDay, partlyCloudy, mist, fog, cloudy, overcast, lightRainShower, drizzle, lightRain, heavyRainShower, heavyRain, sleetShower, sleet, hailShower, hail, lightSnow Shower, lightSnow, heavySnowShower, heavySnow, thunderShower, thunder**  | M                  | N           |
| visibility          | Text                           | A choice from an enumerated list. One of **unknown, veryPoor, poor, moderate, good, veryGood, excellent.**                                                                                                                                                                | M                  | N           |
| name                | Text                           | The name of the weather observation location.                                                                                                                                                                                                                             | M                  | Y           |
| address             | PostalAdresss                  | The weather observed location encoded as a Schema.org Postal Address.                                                                                                                                                                                                     <br><br>[https://schema.org/PostalAddress](https://schema.org/Address)                                                                                                                                                                                                             | M                  | Y           |
| temperature         | Number or ExtQuantitativeValue | The recorded temperature expressed in degrees Celsius, encoded as a Number OR a ExtQuantitativeValue.                                                                                                                                                                     | M                  | Y           |
| refPointOfInterest  | List of Reference              | A JSON encode sequence of characters referencing the unique ids of the associated group of pointOfInterests.                                                                                                                                                              | O                  | Y           |
| windDirection       | Number or ExtQuantitativeValue | The wind direction expressed in degrees compared to geographic North (measured clockwise), encoded as a Number OR a ExtQuantitativeValue.                                                                                                                                 | O                  | Y           |
| windSpeed           | Number or ExtQuantitativeValue | The observed wind speed in m/s, encoded as a Number OR a ExtQuantitativeValue.                                                                                                                                                                                            | O                  | Y           |
| relativeHumidity    | Number or ExtQuantitativeValue | The relative humidity expressed a number between                                                                                                                                                                                                                          <br><br>0 ≤ RelativeHumidity ≤ 1 representing the range 0% to 100%, encoded as a Number OR a ExtQuantitativeValue.                                                                                                                                                                 | O                  | Y           |
| dewPoint            | Number Or ExtQuantitativeValue | The dew point in degrees Celsius, encoded as a Number OR a ExtQuantitativeValue.                                                                                                                                                                                          | O                  | Y           |
| atmosphericPressure | Number Or ExtQuantitativeValue | The measured barometric or atmospheric pressure in units of hecto Pascals, encoded as a Number OR a ExtQuantitativeValue.                                                                                                                                                 | O                  | Y           |
| pressureTendency    | Text Or ExtQuantitativeValue   | Is the pressure is rising or falling, encoded as Text OR a ExtQuantitativeValue. A choice from an enumerated list.                                                                                                                                                        <br><br>One of:                                                                                                                                                                                                                                                                    <br><br>**rising, falling, steady**.                                                                                                                                                                                                                                               | O                  | Y           |

#### WeatherObserved JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/f592f7923c97cd5c6d18bc44a42b7050>
```json
{
  "id": "adb144fb-e732-4944-a192-8690bd17de8c",
  "type": "WeatherObserved",
  "dateCreated": {
    "value": "2016-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "dateModified": {
    "value": "2016-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "source": {
    "value": "http://www.example.com",
    "type": "URL"
  },
  "dataProvider": {
    "value": "OperatorA",
    "type": "Text"
  },
  "schemaVersion": {
    "value": "1.0",
    "type": "Text"
  },
  "location": {
    "value": {
      "type": "Point",
      "coordinates": [
        -104.99404,
        39.75621
      ]
    },
    "type": "geo:json"
  },
  "refDevice": {
    "value": [
      "c3e30a5a-2697-407d-908d-02a627d32730",
      "08d22ce9-ce65-46a6-8e3c-12aa3a5389de"
    ],
    "type": "List"
  },
  "dateObserved": {
    "value": "2016-08-16T10:18:16Z",
    "type": "DateTime"
  },
  "weatherType": {
    "value": "sunnyDay",
    "type": "Text"
  },
  "visibility": {
    "value": "veryGood",
    "type": "Text"
  },
  "name": {
    "value": "London City",
    "type": "Text"
  },
  "address": {
    "type": "PostalAddress",
    "value": {
      "addressLocality": "London",
      "postalCode": "EC4N 8AF",
      "streetAddress": "25 Walbrook"
    }
  },
  "temperature": {
    "value": {
      "value": 15,
      "unitCode": "CEL"
    },
    "type": "ExtQuantitativeValue"
  },
  "refPointofInterest": {
    "value": [
      "b397c472-1ca8-4605-8d35-2fb27e85c0e8",
      "e7c4d076-7eec-45b2-8982-9cd4c331e491"
    ],
    "type": "List"
  },
  "windDirection": {
    "value": {
      "value": 122,
      "unitCode": "DD"
    },
    "type": "ExtQuantitativeValue"
  },
  "windSpeed": {
    "value": {
      "value": 3,
      "unitCode": "MTS"
    },
    "type": "ExtQuantitativeValue"
  },
  "relativeHumidity": {
    "value": {
      "value": 0.2,
      "unitCode": "C62"
    },
    "type": "ExtQuantitativeValue"
  },
  "dewPoint": {
    "value": {
      "value": 44,
      "unitCode": "CEL"
    },
    "type": "ExtQuantitativeValue"
  },
  "atmosphericPressure": {
    "value": {
      "value": 1013.25,
      "unitCode": "A97"
    },
    "type": "ExtQuantitativeValue"
  },
  "pressureTendency": {
    "value": "rising",
    "type": "Text"
  }
}
```
