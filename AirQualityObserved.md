###AirQualityObserved

This entity contains a harmonised description of the air quality observed at a particular location and time. This entity is primarily associated with the vertical segment of the environment and may also be used in smart homes, smart cities, agriculture, industry and related IoT applications.

&lt;AirQualityObserved&gt;&lt;Generic Attributes&gt;

| Attribute Name | Attribute Type | Description                                                                                                                                                                                                                             | Mandatory/ Optional | May be Null |
|----------------|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|-------------|
| id             | Text           | Unique id of this instance of this entity.                                                                                                                                                                                              | M                  | N           |
| type           | Text           | Must be equal to "**AirQualityObserved**".                                                                                                                                                                                              | M                  | N           |
| dateCreated    | DateTime       | Entity creation timestamp.                                                                                                                                                                                                              | M                  | N           |
| dateModified   | DateTime       | Timestamp of the last modification of the entity.                                                                                                                                                                                       | M                  | Y           |
| source         | Text           | A sequence of characters giving the source of the entity data as a URL.                                                                                                                                                                 | M                  | Y           |
| dataProvider   | Text           | A sequence of characters identifying the originator of the harmonised entity.                                                                                                                                                           | M                  | Y           |
| schemaVersion  | Text           | Indicates the version number of the data entity via a sequence of characters of the form "M.N" where M is a sequence of digits representing the major version number and N is a sequence of digits representing a minor version number. | O                  | Y           |

&lt;AirQualityObserved&gt;&lt;Entity Specific Attributes&gt;

| Attribute Name | Attribute Type       | Description                                                                                                   | Mandatory/ Optional | May be Null |
|----------------|----------------------|---------------------------------------------------------------------------------------------------------------|-----|-------------|
| refPOI         | Reference            | A reference to the unique ids of the Point of Interest (monitoring station) that originated this observation. | O   | Y           |
| refDevice      | List of Reference    | A list of references to the unique ids of the devices that originated this observation.                       | O   | Y           |
| location       | geo:json             | The geo:json encoded polygon or point location, of this observation.                                          | M   | N           |
| dateObserved   | DateTime             | The date and time of this observation in ISO8601 UTC format.                                                  | O   | Y           |
| PM2.5          | ExtQuantitativeValue | **value --- Measured value**                                                                                  <br><br>**timestamp --- date and time when measurement was taken**                                                   <br><br>**unitCode --- normally GQ**           <br><br>**unitText --- normally microgram per cubic metre**                                                            | O   | Y           |
| PM10           | ExtQuantitativeValue | **value --- Measured value**                                                                                  <br><br>**timestamp --- date and time when measurement was taken**                                                     <br><br>**unitCode --- normally GQ**                                                                                   <br><br>**unitText --- normally microgram per cubic metre**                                                            | O   | Y           |
| CO             | ExtQuantitativeValue | **value --- Measured value**                                                                                  <br><br>**timestamp --- date and time when measurement was taken**                                                     <br><br>**unitCode --- normally GQ**                                                                                   <br><br>**unitText --- normally microgram per cubic metre**                                                            | O   | Y           |
| O3             | ExtQuantitativeValue | **value --- Measured value**                                                                                  <br><br>**timestamp --- date and time when measurement was taken**                                                     <br><br>**unitCode --- normally GQ**                                                                                   <br><br>**unitText --- normally microgram per cubic metre**                                                            | O   | Y           |
| SO2            | ExtQuantitativeValue | **value --- Measured value**                                                                                  <br><br>**timestamp --- date and time when measurement was taken**                                                     <br><br>**unitCode --- normally GQ**                                                                                   <br><br>**unitText --- normally microgram per cubic metre**                                                            | O   | Y           |
| NO             | ExtQuantitativeValue | **value --- Measured value**                                                                                  <br><br>**timestamp --- date and time when measurement was taken**                                                     <br><br>**unitCode --- normally GQ**                                                                                   <br><br>**unitText --- normally microgram per cubic metre**                                                            | O   | Y           |
| NO2            | ExtQuantitativeValue | **value --- Measured value**                                                                                  <br><br> **timestamp --- date and time when measurement was taken**                                                     <br><br>**unitCode --- normally GQ**                                                                                   <br><br>**unitText --- normally microgram per cubic metre**                                                            | O   | Y           |
| NOx            | ExtQuantitativeValue | **value --- Measured value**                                                                                  <br><br>**timestamp --- date and time when measurement was taken**                                                      <br><br>                  **unitCode --- normally GQ**         <br><br>**unitText --- normally microgram per cubic metre**                                                            | O   | Y           |
| AQI            | Number               | Air Quality Index calculated according to the US EPA standard[1]                                              | O   | Y           |
| measurand      | List of Text         | An array containing a JSON encoded sequence of characters of the measurand observed.                          <br><br>**measurand** , **observedValue**, **unitcode**, **description**.                                              <br><br>Unitcode defined as in schema.org/QuantitativeValue                                                   <br><br>The unit of measurement given using the UN/CEFACT Common Code (3 characters)                                   <br><br><http://wiki.goodrelations-vocabulary.org/Documentation/UN/CEFACT_Common_Codes>                           <br><br>Example;                            <br><br>**"CO,500,GQ,Carbon Monoxide"**      <br><br>**"NO,45,GQ,Nitrogen Monoxide"**     <br><br>**"NOx,139,GQ,Nitrogen oxides"**                                                                               | O   | Y           |

#### AirQualityObserved JSON

The JSON code can be downloaded from:

<https://gist.github.com/GSMADeveloper/xxxxxxxx>TBC
```json
{
  "id": "c9f32b35-a185-48e2-835f-c521efc294ab",
  "type": "AirQualityObserved",
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
  "refPOI": {
    "value": [
      "cdfd9cb8-ae2b-47cb-a43a-b9767ffd5c84"
    ],
    "type": "List"
  },
  "refDevice": {
    "value": [
      "5c9fb9dd-fc13-4fda-8f4c-f99a04f6f858"
    ],
    "type": "List"
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
  "dateObserved": {
    "value": "2016-08-08T10:18:16Z",
    "type": "DateTime"
  },
  "PM2.5": {
    "type": "ExtQuantitativeValue",
    "value": {
      "value": 187,
      "unitCode": "GQ"
    }
  },
  "PM10": {
    "type": "ExtQuantitativeValue",
    "value": {
      "value": 50,
      "unitCode": "GQ"
    }
  },
  "CO": {
    "type": "ExtQuantitativeValue",
    "value": {
      "value": 0.8,
      "unitCode": "GQ"
    }
  },
  "O3": {
    "type": "ExtQuantitativeValue",
    "value": {
      "value": 300,
      "unitCode": "GQ"
    }
  },
  "SO2": {
    "type": "ExtQuantitativeValue",
    "value": {
      "value": 7,
      "unitCode": "GQ"
    }
  },
  "NO": {
    "type": "ExtQuantitativeValue",
    "value": {
      "value": 137,
      "unitCode": "GQ"
    }
  },
  "NO2": {
    "type": "ExtQuantitativeValue",
    "value": {
      "value": 63,
      "unitCode": "GQ"
    }
  },
  "NOx": {
    "type": "ExtQuantitativeValue",
    "value": {
      "value": 273,
      "unitCode": "GQ"
    }
  },
  "AQI": {
    "type": "Number",
    "value": 238
  },
  "measurand": {
    "value": [
      "PM2.5,187.0,GQ,Particulate Matter 2.5",
      "PM10,50.0,GQ,Particulate Matter 10",
      "CO,0.8,GQ,Carbon Monoxide",
      "O3,300.0,GQ,Ozone",
      "SO2,7.0,GQ,Sulfur Dioxide",
      "NO,137.0,GQ,Nitrogen Monoxide",
      "NO2,63.0,GQ,Nitrogen Dioxide",
      "NOx,273.0,GQ,Nitrogen oxides"
    ],
    "type": "List"
  }
}
```
