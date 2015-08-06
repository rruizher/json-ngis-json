# json-ngis-json
Camel route to transform a json input in a different json data structure.	
It uses 2 unmarshallers from Jackson library and a custom Camel processor to adapt from a POJO to another POJO and then in final JSON file.

![alt tag](https://cloud.githubusercontent.com/assets/7669634/9110646/a4163274-3c3f-11e5-982c-51275c66cd92.png)




To use clone the repository and
``` mvn camel:run ```

Transforms from:
```
  { 
	"number":233,
	"name":"233_SAN_JUAN_BOSCO_SANTIAGO_RUSIÃ‘OL",
	"address":"San Juan Bosco - Santiago RusiÃ±ol",	
	"banking":true,
	"bonus":false,
	"status":"OPEN",
	"contract_name":"Valence",
	"bike_stands":15,
	"available_bike_stands":1,
	"available_bikes":11,
	"last_update":1436397064000
  }
```

To:
```
  {
	"contextElements": [
		{
			"type": "Station",
			"isPattern": "false",
			"id": "233_SAN_JUAN_BOSCO_SANTIAGO_RUSIÃ‘OL",
			"attributes": [
			{
				"name": "number",
				"type": "integer",
				"value": "233"
			},
			{
				"name": "name",
				"type": "string",
				"value": "233_SAN_JUAN_BOSCO_SANTIAGO_RUSIÃ‘OL"
			},
			{
				"name": "address",
				"type": "string",
				"value": "San Juan Bosco - Santiago RusiÃ±ol"
			},
			{
				"name": "banking",
				"type": "boolean",
				"value": "true"
			},
			{
				"name": "bonus",
				"type": "boolean",
				"value": "false"
			},
			{
				"name": "status",
				"type": "string",
				"value": "OPEN"
			},
			{
				"name": "contract_name",
				"type": "string",
				"value": "Valence"
			},
			{
				"name": "bike_stands",
				"type": "integer",
				"value": "15"
			},
			{
				"name": "available_bike_stands",
				"type": "integer",
				"value": "4"
			},
			{
				"name": "available_bikes",
				"type": "integer",
				"value": "11"
			},
			{
				"name": "last_update",
				"type": "string",
				"value": "1436397064000d"
			}
		    ]
		}
	],
	"updateAction": "APPEND"
  }
```
