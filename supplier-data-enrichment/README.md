# Supplier Data Enrichment #
### Request:
#### Method & Path: POST /inventory/enrich
#### url: http://localhost:8081/inventory/enrich
#### body:
```
[
  {"partId": "P-01", "name": "Clutch Cable", "unitPrice": 1200, "qtyNeeded": 10, "supplierId": "SUP-COL"},
  {"partId": "P-02", "name": "Spark Plug", "unitPrice": 450, "qtyNeeded": 50, "supplierId": "SUP-IND"},
  {"partId": "P-03", "name": "Brake Fluid", "unitPrice": 850, "qtyNeeded": 5, "supplierId": "SUP-COL"}
]

```
### Response:
```
{
	"reportType": "Local Supplier Restock Orders",
	"orders": [
		{
			"partNumber": "P-01",
			"partName": "Clutch Cable",
			"quantity": 10,
			"lineTotal": 12000,
			"supplierDetails": {
				"id": "SUP-COL",
				"name": "Colombo Auto Components Ltd",
				"country": "LK"
			}
		},
		{
			"partNumber": "P-03",
			"partName": "Brake Fluid",
			"quantity": 5,
			"lineTotal": 4250,
			"supplierDetails": {
				"id": "SUP-COL",
				"name": "Colombo Auto Components Ltd",
				"country": "LK"
			}
		}
	]
}
```