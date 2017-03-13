### Road

This entity contains a harmonised geographic and contextual description of a Road. Roads are made up of one or more RoadSegment entities. This entity is primarily associated with the Automotive and Smart City vertical segments and related IoT applications.

&lt;Road&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                             | Mandatory/ Optional | May be Null |
|----------------|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                              | M                  | N           |
| type           | Text           | Must be equal to "**Road**".                                                                                                                                                                                                            | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                              | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                       | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                 | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                           | M                  | Y           |
| schemaVersion  | Text           | Indicates the version number of the data entity via a sequence of characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. | O                  | Y           |

&lt;Road&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type    | Description                                                                                                         | Mandatory/ Optional | May be Null |
|----------------|-------------------|---------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| country        | Text              | The country in which this road is in                                                                                | M                  | N           |
| refRoadSegment | List of Reference | A JSON encode sequence of characters referencing the unique ids of the group of roadSegments that define this road. | M                  | Y           |
| roadClass      | Text              | The official classification of this road (relevant to the local country).                                           | M                  | Y           |
| name           | Text              | The official designation of this road.                                                                              | M                  | Y           |
| alternateName  | Text              | An alternative name for this road.                                                                                  | O                  | Y           |

#### Road JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/aa8dc76b8702be6e0f9509563c308861>
```json
{
  "id": "19b6f4b7-a9b4-4114-8391-3133bf96aedc",
  "type": "Road",
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
  "country": {
    "value": "United Kingdom",
    "type": "Text"
  },
  "refRoadSegment": {
    "value": [
      "2a982120-4d98-425b-a8db-1de5563db6a8",
      "43e255c7-262e-4d6d-95a1-69a53e37dcc0"
    ],
    "type": "List"
  },
  "roadClass": {
    "value": "Dual Carriageway",
    "type": "Text"
  },
  "name": {
    "value": "M1",
    "type": "Text"
  },
  "alternateName": {
    "value": "M1 Motorway",
    "type": "Text"
  }
}
```
