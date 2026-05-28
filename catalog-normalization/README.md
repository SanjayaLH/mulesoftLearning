# Paginated Catalog Normalizer #
### Request:
#### Method & Path: POST /catalog/normalize
#### url: http://localhost:8081/catalog/normalize
#### body:
```
{
  "pagination": {
    "currentPage": 3,
    "itemsPerPage": 2,
    "totalItems": 15
  },
  "records": [
    {"sku": "BRAKE-01", "details": {"name": "Front Brake Pad", "cost": 4000}},
    {"sku": "WIPER-12", "details": {"name": "Silicone Wiper Blade", "cost": 1500}}
  ]
}

```
### Response:
```
{
	"syncStatus": "SUCCESS",
	"navigation": {
		"activePage": 3,
		"totalPages": 8,
		"hasMorePages": true
	},
	"products": [
		{
			"partNumber": "BRAKE-01",
			"displayName": "Front Brake Pad",
			"supplierCost": 4000,
			"retailPriceLKR": 4600
		},
		{
			"partNumber": "WIPER-12",
			"displayName": "Silicone Wiper Blade",
			"supplierCost": 1500,
			"retailPriceLKR": 1725
		}
	]
}
```