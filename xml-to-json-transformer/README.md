# XML to-JSON Transformer #
### Request:
#### Method & Path: POST /inventory/legacy-import
#### url: http://localhost:8081/inventory/legacy-import
#### body:
```
<?xml version="1.0" encoding="UTF-8"?>
<order id="ORD-9921">
    <customer>
        <company>Lanka Auto Masters</company>
        <contactInfo>
            <phone>0112345678</phone>
        </contactInfo>
    </customer>
    <partsList>
        <part type="mechanical">
            <sku>SKU-882</sku>
            <description>Shock Absorber</description>
            <cost>4500</cost>
        </part>
        <part type="electrical">
            <sku>SKU-104</sku>
            <description>Headlight Bulb</description>
            <cost>1200</cost>
        </part>
    </partsList>
</order>

```
### Response:
```
{
	"importMetadata": {
		"orderReference": "ORD-9921",
		"buyerCompany": "Lanka Auto Masters",
		"buyerContact": "0112345678"
	},
	"processedParts": [
		{
			"partSku": "SKU-882",
			"name": "Shock Absorber",
			"category": "mechanical",
			"basePrice": 4500
		},
		{
			"partSku": "SKU-104",
			"name": "Headlight Bulb",
			"category": "electrical",
			"basePrice": 1200
		}
	]
}
```