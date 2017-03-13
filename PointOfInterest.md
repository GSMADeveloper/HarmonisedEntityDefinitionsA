### PointOfInterest

This entity contains a harmonised geographic description of a Point of Interest. This entity is used in applications that use spatial data and is applicable to Automotive, Environment, Industry and Smart City vertical segments and related IoT applications.

&lt;PointOfInterest&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                             | Mandatory/ Optional | May be Null |
|----------------|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                              | M                  | N           |
| type           | Text           | Must be equal to "**PointOfInterest**".                                                                                                                                                                                                 | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                              | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                       | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                 | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                           | M                  | Y           |
| schemaVersion  | Text           | Indicates the version number of the data entity via a sequence of characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. | O                  | Y           |

&lt;PointOfInterest&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                              | Mandatory/ Optional | May be Null |
|----------------|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| location       | geo:json       | The geo:json encoded map location (point or polygon or multi-polygon), of this point of interest.                                                                        | M                  | N           |
| category       | List           | A JSON encoded List of one or more sequence of characters describing categories associated with this point of interest. A choice from:                                   <br><br>**church, school, town hall, distinctiveBuilding, postOffice, shop, postBox, telephoneBox, pub, car park, lay-bye, speedCamera, restaurant, tourist attraction, other.**  | M                  | Y           |
| description    | Text           | An optional description of the entity.                                                                                                                                   | O                  | Y           |
| place          | Place          | The schema.org place definition for this Point Of Interest. See <https://schema.org/Place>                                                                               | O                  | Y           |

#### PointOfInterest JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/4cd7203d66ccf2caf2123cf4519f5f74>
```json
{
  "id": "44e47705-90c3-4dbc-a0ae-7810306de5e9",
  "type": "PointOfInterest",
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
  "category": {
    "value": [
      "school"
    ],
    "type": "List"
  },
  "description": {
    "value": "Learn all about mobile at the GSMA Academy",
    "type": "Text"
  },
  "place": {
    "type": "Place",
    "value": {
      "name": "GSMA Academy",
      "address": {
        "type": "PostalAddress",
        "addressLocality": "London",
        "postalCode": "EC4N 8AF",
        "streetAddress": "25 Walbrook"
      },
      "telephone": "0212345678"
    }
  }
}
```
