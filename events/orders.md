# Orders

## Order Purchase

{% hint style="danger" %}
Sending in Order Purchase events via the SDK should be accompanied by an Order Purchase event via the Event API. This ensures that ad blockers do not block the purchase event, but ensures attribution data is collected on as many orders as possible. Zaius will de-dupe the purchases.
{% endhint %}

```javascript
zaius.event("order", {
  "action": "purchase",
  "data": {
    "order": {
      "order_id": "OR345",
      "total": 109.65,
      "discount": 5.00,
      "subtotal": 103.00,
      "tax": 5.15,
      "shipping": 6.50,
      "coupon_code": "5OFF",
      "items": [
        {
          "product_id": "2045",
          "price": 19.00,
          "quantity": 5,
          "discount": 0.00,
          "subtotal": 95.00
        },
        {
          "product_id": "2091",
          "price": 10.00,
          "quantity": 1,
          "discount": 2.00,
          "subtotal": 8.00
        }
      ]
    }
  }
});
```

## Refunds / Returns / Cancellations

{% hint style="danger" %}
Zaius only supports sending Order **refunds**, **returns** & **cancellations** via API or CSV to ensure that ad blockers do not block these critical events.
{% endhint %}

