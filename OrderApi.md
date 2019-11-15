# Order API

#### [GET] /orders?from={date}&to={date}&orderStatus={status}
orderStatus(optional) - if not specified return orders with all order statuses
```JSON
{
  "data": [
    {
      "id": "123456",
      "created_at": "2008-01-10T11:00:00-05:00",
      "order_status": "paid",
      "currency": "USD",
      "total_price": 109.99,
      "subtotal_price": 99.99
    }
  ]
}
```
