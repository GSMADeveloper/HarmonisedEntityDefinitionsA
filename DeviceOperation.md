### DeviceOperation

This entity contains a harmonised description of a generic device operation entity. The device operation entity contains dynamic data reported by a device and is therefore applicable to all IoT segments and related IoT applications.

&lt;DeviceOperation&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                             | Mandatory/Optional | May be Null |
|----------------|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                              | M                  | N           |
| type           | Text           | Must be equal to "**DeviceOperation**".                                                                                                                                                                                                 | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                              | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                       | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                 | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                           | M                  | Y           |
| schemaVersion  | Text           | Indicates the version number of the data entity via a sequence of characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. | O                  | Y           |

&lt;DeviceOperation&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                    | Mandatory/Optional | May be Null |
|----------------|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| refDevice      | Reference      | The unique entity Id of the device to which this device operation relates.                                                                                     | M                  | N           |
| operationType  | List           | Choice form an enumerated list including:                                                                                                                      <br><br>**event, maintenance, fault, installation, upgrade, other.**                                                                                                    | O                  | Y           |
| description    | Text           | A description of the operation.                                                                                                                                | O                  | Y           |
| result         | Text           | A description of the results of the operation. One of                                                                                                          <br><br>**ok**, **aborted, failed**                                                                                                                                     | O                  | Y           |
| startDate      | DateTime       | The planned start timestamp for the operation.                                                                                                                 | M                  | Y           |
| endDate        | DateTime       | The planned end timestamp for the operation. Note that this is advisory and the actual time the operation finishes may be before or after the planned endDate. | M                  | Y           |
| status         | Text           | A choice from an enumerated list describing the status. One of:                                                                                                <br><br>**planned, ongoing, finished, scheduled, cancelled.**                                                                                                           | O                  | Y           |
| operator       | Person         | The operator performing this action encoded as a Schema.org person.                                                                                            <br><br><https://schema.org/Person>                                                                                                                                     | O                  | Y           |
| dateStarted    | DateTime       | Timestamp when the operation actually started to be performed.                                                                                                 | O                  | Y           |
| dateFinished   | DateTime       | Timestamp when the operation actually finished.                                                                                                                | O                  | Y           |
| dateReported   | DateTime       | The timestamp when the device event or fault was reported.                                                                                                     | O                  | Y           |
| dateAddressed  | DateTime       | The timestamp when the event or fault was addressed or cleared.                                                                                                | O                  | Y           |

#### DeviceOperation JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/581d2de918e01fb05efd35f27686f361>
```json
{
  "id": "27577638-bd8a-4732-b418-fc8b949a0b0f",
  "type": "DeviceOperation",
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
  "refDevice": {
    "value": "2033a7c7-d31b-48e7-91c2-014dc426c29e",
    "type": "Reference"
  },
  "operationType": {
    "value": [
      "fault"
    ],
    "type": "List"
  },
  "description": {
    "value": "Backup battery needs replacement",
    "type": "Text"
  },
  "result": {
    "value": "ok",
    "type": "Text"
  },
  "startDate": {
    "value": "2016-08-20T10:18:16Z",
    "type": "DateTime"
  },
  "endDate": {
    "value": "2016-08-18T14:18:16Z",
    "type": "DateTime"
  },
  "status": {
    "value": "ongoing",
    "type": "Text"
  },
  "operator": {
    "value": {
      "givenName": "John Dee"
    },
    "type": "Person"
  },
  "dateStarted": {
    "value": "2016-08-20T10:18:16Z",
    "type": "DateTime"
  },
  "dateFinished": {
    "value": "2016-08-18T10:18:16Z",
    "type": "DateTime"
  },
  "dateReported": {
    "value": "2016-08-18T10:18:16Z",
    "type": "DateTime"
  }
}
```
