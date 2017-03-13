### ProductRecord

This entity contains a harmonised description of the conditions recorded as a generic Product moves through the supply chain. This entity is primarily associated with the retail supply vertical and related IoT applications.

&lt;ProductRecord&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                             | Mandatory/ Optional | May be Null |
|----------------|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                              | M                  | N           |
| type           | Text           | Must be equal to "**ProductRecord**".                                                                                                                                                                                                   | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                              | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                       | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                 | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                           | M                  | Y           |
| schemaVersion  | Text           | Indicates the version number of the data entity via a sequence of characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. | O                  | Y           |

&lt;ProductRecord&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name      | Attribute Type               | Description                                                                                  | Mandatory/ Optional | May be Null |
|---------------------|------------------------------|----------------------------------------------------------------------------------------------|--------------------|-------------|
| refProduct          | Reference                    | Unique id of the Product to which this record relates.                                       | M                  | N           |
| location            | geo:json                     | The geo:json encoded current location.                                                       | M                  | N           |
| temperature         | ExtQuantitativeValue(Number) | The observed local air temperature in degrees centigrade encoded as an ExtQuantitativeValue. | O                  | Y           |
| relativeHumidity    | ExtQuantitativeValue(Number) | Relative Humidity a number between 0 and 1 representing the range 0% to 100 (%)              <br><br>0 ≤ relativeHumidity ≤ 1 encoded as a ExtQuantitativeValue.                                   | O                  | Y           |
| atmosphericPressure | ExtQuantitativeValue(Number) | Atmospheric Pressure in units of hecto Pascals encoded as a ExtQuantitativeValue.            | O                  | Y           |
| description         | Text                         | Description of this ProductRecord.                                                           | O                  | Y           |

#### ProductRecord JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/xxxxxxxx>TBC
```json
{
  "id": "85d05a21-6907-44b3-83d8-85d8a713d003",
  "type": "ProductRecord",
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
  "refProduct": {
    "type": "Reference",
    "value": "6223903a-d8c5-4e7e-af24-cc90967feb61"
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
  "temperature": {
    "type": "ExtQuantitativeValue",
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "unitCode": "CEL",
      "value": 3.823
    }
  },
  "relativeHumidity": {
    "type": "ExtQuantitativeValue",
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "unitCode": "C62",
      "value": 0.7
    }
  },
  "atmosphericPressure": {
    "type": "ExtQuantitativeValue",
    "value": {
      "timestamp": "2016-08-08T10:18:16Z",
      "unitCode": "A97",
      "value": 1006.19
    }
  },
  "description": {
    "type": "Text",
    "value": "Palm oil consignment arrived at port for shipment"
  }
}
```
