# Product

{% hint style="danger" %}
`product_id` is required on all events with an event type of `product`
{% endhint %}

## Details Viewed

```javascript
zaius.event("product", { action: "detail", product_id: "product-2143" });
```

## Listing Viewed

```javascript
zaius.event("product", { action: "listing", product_id: "product-2143" });
```

## Add to Cart

```javascript
zaius.event("product", { action: "add_to_cart", product_id: "product-2143" });
```

## Remove from Cart

```javascript
zaius.event("product", { action: "remove_from_cart", product_id: "product-2143" });
```

