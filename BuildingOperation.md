### BuildingOperation

This entity contains a harmonised description of a generic operation (related to smart buildings) applied to the referenced building. The building operation contains dynamic data reported by, or associated with a building or operations applicable to the building. This entity is associated with the vertical segments of smart homes, smart cities, industry and related IoT applications.

&lt;BuildingOperation&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                             | Mandatory/ Optional | May be Null |
|----------------|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                              | M                  | N           |
| type           | Text           | Must be equal to "**BuildingOperation**".                                                                                                                                                                                               | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                              | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                       | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                 | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                           | M                  | Y           |
| schemaVersion  | Text           | Indicates the version number of the data entity via a sequence of characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. | O                  | Y           |

&lt;BuildingOperation&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name              | Attribute Type    | Description                                                                                                                                                    | Mandatory/ Optional | May be Null |
|-----------------------------|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| refBuilding                 | Reference         | Refers to the unique entity Id of the building to which this building record relates.                                                                          | M                  | N           |
| operationType               | Text              | Defines the type of operation conducted/ requested. This will be one of a defined list of operation types specific to the building.                            | O                  | Y           |
| description                 | Text              | A description of the operation.                                                                                                                                | O                  | Y           |
| result                      | Text              | A description of the results of the operation. One of                                                                                                          <br><br>**ok, aborted, failed**                                                                                                                                         | O                  | Y           |
| startDate                   | DateTime          | The planned start timestamp for the operation.                                                                                                                 | M                  | Y           |
| endDate                     | DateTime          | The planned end timestamp for the operation. Note that this is advisory and the actual time the operation finishes may be before or after the planned endDate. | M                  | Y           |
| status                      | Text              | A choice from an enumerated list describing the status. One of:                                                                                                <br><br> **planned, ongoing, finished, scheduled, cancelled**                                                                                                            | O                  | Y           |
| operator                    | Person            | The operator performing this action encoded as a Schema.org person.                                                                                            <br><br><https://schema.org/Person>                                                                                                                                     | O                  | Y           |
| dateStarted                 | DateTime          | Timestamp when the operation actually started to be performed.                                                                                                 | O                  | Y           |
| dateFinished                | DateTime          | Timestamp when the operation actually finished.                                                                                                                | O                  | Y           |
| operationSequence           | Text              | The sequence of operations executed/ requested for the building in a representation format relevant to the building.                                           | O                  | Y           |
| refRelatedBuildingOperation | List of Reference | An List containing a JSON encoded sequence of characters referencing the unique ids of any related building operations.                                        | O                  | Y           |
| refRelatedOperation         | List of Reference | An List containing a JSON encoded sequence of characters referencing the unique ids of any related operations (device, machine or other).                      | O                  | Y           |

#### BuildingOperation JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/2c15fe4070fbbf5ed5227ccabf19b639>
```json
{
  "id": "57b912ab-eb47-4cd5-bc9d-73abece1f1b3",
  "type": "BuildingOperation",
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
  "refBuilding": {
    "value": "f59e2074-0032-4ccd-b0dd-f06370ffb6af",
    "type": "Reference"
  },
  "operationType": {
    "value": "Air Conditioning Switch To Low Power",
    "type": "Text"
  },
  "description": {
    "value": "Air conditioning levels reduced due to out of hours",
    "type": "Text"
  },
  "result": {
    "value": "Operation successful",
    "type": "Text"
  },
  "startDate": {
    "value": "2016-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "endDate": {
    "value": "2016-08-20T10:18:16Z",
    "type": "DateTime"
  },
  "status": {
    "value": "planned",
    "type": "Text"
  },
  "dateStarted": {
    "value": "2016-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "dateFinished": {
    "value": "2016-08-20T10:18:16Z",
    "type": "DateTime"
  },
  "operationSequence": {
    "value": "Fan levels reduced to minimum. Target temperature set to 24 degrees Celsius. ",
    "type": "Text"
  },
  "refRelatedBuildingOperation": {
    "value": [
      "b4fb8bff-1a8f-455f-8cc0-ca43c069f865onService1",
      "55c24793-3437-4157-9bda-667c9e1531fc"
    ],
    "type": "List"
  },
  "refRelatedOperation": {
    "value": [
      "36744245-6716-4a28-84c7-0e3d7520f143",
      "33b2b713-9223-40a5-87a0-3f80a1264a6c"
    ],
    "type": "List"
  }
}
```
