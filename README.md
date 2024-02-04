# Rick Egdorf 

*Senior Technical Writer specializing in API Reference Documentation*

***

## Work Samples

### API Field Definitions {#api-field-defs}

The following example shows ambiguous field definitions and more useful, descriptive definitions.

**Sample JSON**

```
{ 
  "addressList": [
    {
      "address1": "string",
      "address2": "string",
      "city": "string",
      "country": "string",
      "postalcode": "string",
      "state": "string" 
    } 
  ], 
  "languageList": [
    {
     "languageCode": "string", 
     "languageUse": "string" 
    }
  ], 
  "clientAffiliation": [ 
    { 
      "billingPrefID": "int", 
      "effectiveDate": "string", 
      "expirationDate": "string" 
    }
  ],
  "data": [
    "holdStatus": "boolean"
    ]	
}
```

**Field Definitions Table**

The following table shows field definition examples for the preceding JSON file. The column labeled "More Useful Definitions" adds clarity and meaning for the target audience.

|Object |Ambiguous Definition |More Useful Definition |
|---|---|---|
|addressList  |Address data  |An object that contains details about the client's address.  |
|addressList.clientName |Client name  |Name of the client.  |
|addressList.address1  |Address  |First line of the client's address.<br>Maximum: 55 characters.  |
|addressList.address2  |Address |Additional address line, if needed. Examples: apartment number, PO box, care of address.<br>Maximum: 55 characters  |
|addressList.country |Country name |Name of the country of the client's address. Country codes are defined by the International Organization for Standardization (ISO). <br>	Maximum: 3 characters. | 
|addressList.postalcode  |zipcode |Five-digit postal code for a U.S. location. **Note:** U.S. postal codes may also contain a hyphen and the four-digit extension.<br>Maximum: 20 characters.  | 
|addressList.state  |State  |Name of the city of the client’s address.<br>Maximum: 50 characters.  |
|languageList  |Language data |An object that contains details about the client's preferred language and any other languages used by the client’s employees.  |
|languageList.languageCode  |Language code |A numeric code that indicates the client's language preference.<br>Maximum: 2 characters. |
|languageList.languageUse  |Indicates language used  |A numeric code that indicates the general acceptance of each language by the client’s employees. <ul><li>1: Considered the native language of many or most employees.</li><li>2: Used less often but still spoken by many employees.</li><li>3: Used infrequently.</li></ul>  |
|clientAffiliation  |Client affiliation data  |An object that contains information about the relationship between the client and ABC Corp.  |
|clientAffiliation.billingPrefID  |ID of preferred billing  |The system-generated identifier that represents a billing preference record.  |
|clientAffiliation.effectiveDate |Effective date |Start date of the affiliation record for the client and XYZ Corp. <br> Format: YYYY-MM-DD |
|clientAffiliation.expirationDate |Expiration date  |End date of the affiliation record for the client and XYZ Corp. <br> Format: YYYY-MM-DD   |
|data |Data  |An object that contains information about the contract.  |
|data.holdStatus |Defines holds on contract  |Indicates whether the client has any holds currently applied to the contract. <br>Valid values: <ul><li>0: False (default)</li><li>1: True</li></ul>|

***

### API Field Definitions Generated from Unit Test Field Descriptor JSON Files {#unit-test}

The following example shows API field definitions coded into the unit test field descriptor JSON file. This technique represents a component of a highly efficient and collaborative methodology used to generate accurate, real-time documenation at code deployment. By making Technical Writing and Engineering teams required pull request approvers ensures collaboration and accurate documentation. 

**Sample Unit Test Descriptor File**

```
[
  {
    "path": "requestData",
    "type": "object",
    "length": "",
    "required": true,
    "description": "An object that contains information about the request."
  },
  {
    "path": "requestData.submitterID",
    "type": "string",
    "length": "25",
    "required": true,
    "description": "A unique indentifier for the sender of the request. \n\nMaximum: 25 characters. \n\nValid value: ABC: Landslide."
  },
  {
    "path": "requestData.requests[]",
    "type": "array",
    "length": "",
    "required": true,
    "description": "An array that contains additional data about the request. Typically, the request is for a claim, but is not limited to a claim request."
  }
  ...
]
```

**Output Generated from the Above File**

Following is the data pulled directly from the key value pairs to build the documentation. 

|Path | Type | Length | Required | Description |
|--|--|--|--|--|
| requestData | object |  | true | An object that contains information about the request. |
| requestData.submitterID | string |25 | true |A unique indentifier for the sender of the request. <br>Maximum: 25 characters. <br>Valid value: ABC: Landslide. |
| requestData.requests[] | array | | true | An array that contains additional data about the request. Typically, the request is for a claim, but is not limited to a claim request. |


***

### Error Message Examples {#errors}

Error messages can be clarified, made more useful, and less frustrating to the user by explaining what happened, why it happened, and a solution. If space is limited, word the error message so that those key points are implied.

|Ambiguous Error Message |More Useful Error Message |
|---| ---|
|Invalid format |Please enter a password using the [approved format](url.html). |
|Incorrect format |Please enter your email address in the following format: yourname@example.com  |
|Specified date is incorrect  |Please enter the date in the following format, including the dashes: YYYY-MM-DD  |
|Bad parameter. There was an error in the request |The request payload may have a formatting error. Please review and try submitting again. |
|Invalid JSON in your request  |Either the JSON is invalid or the incorrect ```Content-Type``` header was sent. Please check and try again. |

