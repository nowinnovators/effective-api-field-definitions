# API Field Definitions

Have you ever experienced bad documentation? Whether it's assembling your child's toy or setting up your camera for that once-in-a-lifetime solar eclipse, there is no room for ambiguity. Clearly written API reference documentation is even more important because the target audience is technical and efficiency is key. Following is a sample JSON and the corresponding field definitions table from an API reference guide. Note the useful, descriptive definitions written by a technical writer. Which do you prefer?

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
