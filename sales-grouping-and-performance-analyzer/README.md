# Sales Grouping & Performance Analyzer #
### Request:
#### Method & Path: POST /analytics/branches
#### url: http://localhost:8081/analytics/branches
#### body:
```
[
  {"invoiceId": "INV-01", "branch": "Colombo", "amount": 1500},
  {"invoiceId": "INV-02", "branch": "Kandy", "amount": 800},
  {"invoiceId": "INV-03", "branch": "Colombo", "amount": 2200},
  {"invoiceId": "INV-04", "branch": "Galle", "amount": 3100},
  {"invoiceId": "INV-05", "branch": "Kandy", "amount": 1200}
]

```
### Response:
```
{
  "reportGeneratedAt": "2026-05-25 03:15:51",
  "branchPerformance": [
    {
      "branchName": "Colombo",
      "transactionCount": 2,
      "totalRevenue": 3700
    },
    {
      "branchName": "Kandy",
      "transactionCount": 2,
      "totalRevenue": 2000
    },
    {
      "branchName": "Galle",
      "transactionCount": 1,
      "totalRevenue": 3100
    }
  ],
  "globalMetrics": {
    "totalNetworkRevenue": 8800,
    "averageInvoiceValue": 1760
  }
}
```