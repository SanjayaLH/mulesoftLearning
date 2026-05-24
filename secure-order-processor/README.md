# Secure Order Processor with Validation #
### Request:
#### Method & Path: POST /secure-order
#### url: http://localhost:8081/secure-order
#### body:
```
{
  "customerId": "CUST-8831",
  "phone": "0771234567",
  "items": [
    {"partId": "A10", "qty": 2, "price": 150},
    {"partId": "B20", "qty": 0, "price": 50},
    {"partId": "C30", "qty": 1, "price": -10}
  ]
}
```
### Response:
```
{
  "processingStatus": "Processed",
  "customerMetrics": {
    "id": "CUST-8831",
    "maskedPhone": "*******567"
  },
  "audit": {
    "totalReceived": 3,
    "totalValid": 1,
    "totalInvalid": 2,
    "requiresReview": true
  },
  "validItems": [
    {
      "partId": "A10",
      "lineTotal": 300
    }
  ],
  "invalidItems": [
    {"partId": "B20", "qty": 0, "price": 50},
    {"partId": "C30", "qty": 1, "price": -10}
  ]
}
```