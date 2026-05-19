# Multi-Vendor Order Router #
### Request:
#### Method & Path: POST /process-orders
#### url: http://localhost:8081/process-orders
#### body:
```
[
  {"partId": "LOC-101", "name": "Brake Pad", "priceUSD": 20.00, "quantity": 2},
  {"partId": "IMP-902", "name": "Spark Plug Set", "priceUSD": 45.50, "quantity": 1},
  {"partId": "LOC-204", "name": "Oil Filter", "priceUSD": 12.00, "quantity": 5},
  {"partId": "IMP-551", "name": "Timing Belt", "priceUSD": 110.00, "quantity": 1}
]
```
### Response:
```
{
	"metadata": {
		"timestamp": "2026-05-20T01:50:33Z",
		"totalItems": 4
	},
	"localSupplierOrder": [
		{
			"id": "LOC-101",
			"description": "Brake Pad",
			"qty": 2,
			"costLKR": 12000
		},
		{
			"id": "LOC-204",
			"description": "Oil Filter",
			"qty": 5,
			"costLKR": 18000
		}
	],
	"importedSupplierOrder": [
		{
			"id": "IMP-902",
			"description": "Spark Plug Set",
			"qty": 1,
			"costLKR": 13650
		},
		{
			"id": "IMP-551",
			"description": "Timing Belt",
			"qty": 1,
			"costLKR": 33000
		}
	],
	"totalOrderValueLKR": 76650
}
```