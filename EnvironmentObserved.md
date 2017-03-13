### EnvironmentObserved

This entity contains a harmonised description of the environmental conditions observed at a particular location and time. This entity is primarily associated with the vertical segment of the environment and agriculture but may also be used in smart home, smart cities, industry and related IoT applications.

&lt;EnvironmentObserved&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                             | Mandatory/ Optional | May be Null |
|----------------|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                              | M                  | N           |
| type           | Text           | Must be equal to "**EnvironmentObserved**".                                                                                                                                                                                             | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                              | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                       | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                 | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                           | M                  | Y           |
| schemaVersion  | Text           | Indicates the version number of the data entity via a sequence of characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. | O                  | Y           |

&lt;EnvironmentObserved&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name          | Attribute Type    | Description                                                                                                                        | Mandatory/ Optional | May be Null |
|-------------------------|-------------------|------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| location                | geo:json          | The geo:json encoded map location, of this observation.                                                                            | M                  | N           |
| refWeatherObserved      | List of Reference | An List containing a JSON encoded sequence of characters that reference the unique ids of the related weather entities.            | O                  | Y           |
| refAirQualityObserved   | List of Reference | An List containing a JSON encoded sequence of characters that reference the unique ids of the related AirQualityObserved entities. | O                  | Y           |
| refWaterQualityObserved | List of Reference | An List containing a JSON encoded sequence of characters that reference the unique ids of the related WaterQuality entities.       | O                  | Y           |
| measurand               | List              | An List containing a JSON encoded sequence of characters of the measurand observed.                                                <br><br>**measurand, observedValue, unitCode, description **                                                                               <br><br>UnitCode defined as in schema.org/QuantitativeValue                                                                                 <br><br>The unit of measurement given using the UN/CEFACT Common Code (3 characters) – the unitcode.                                        <br><br><http://wiki.goodrelations-vocabulary.org/Documentation/UN/CEFACT_Common_Codes>                                                     <br><br>Possible examples of typical measurands, descriptions and unitcodes are presented below:                                            <br><br>O2. The level of free, non-compound oxygen present. (*M1*)                                                                          <br><br>Hg. The level of compound mercury present. (*M1*)                                                                                   <br><br> NH4. Concentration of ammonium. (*M1*)                                                                                              <br><br> Cl-. Concentration of chlorides. (*M1*)                                                                                            <br><br> NO3-. Concentration of nitrates. (*M1*)                                                                                            <br><br>etc.                                                                                                                                | O                  | Y           |

#### EnvironmentObserved JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/63d18a7f5845aa201c9470d84b7912f8>
```json
{
  "id": "33f02632-74f4-4c96-9ba1-e26945de9481",
  "type": "EnvironmentObserved",
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
  "refWeatherObserved": {
    "value": [
      "fae29f4c-0691-4bab-bef8-ad1cd165cc28",
      "1c7a2711-ae38-4ea9-8f9f-627067067d53"
    ],
    "type": "List"
  },
  "refAirQualityObserved": {
    "value": [
      "4b8b09c9-ce54-46de-8067-5591e02d8f29",
      "08a14933-b44d-4297-b2d2-2c3f3844012e"
    ],
    "type": "List"
  },
  "refWaterQualityObserved": {
    "value": [
      "68a83e68-61e6-4e3c-975c-5b301c184ca6",
      "b01518e3-2b60-4bbd-9783-3af0d660349e"
    ],
    "type": "List"
  },
  "measurand": {
    "value": [
      "CO, 500, GQ, Carbon Monoxide"
    ],
    "type": "List"
  }
}
```
