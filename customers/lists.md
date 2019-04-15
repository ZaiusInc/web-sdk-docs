---
description: Subscribe and unsubscribe identifiers from messaging Lists.
---

# Messaging Lists

Messaging Lists allow you to group customers for the purposes of tracking their communication preferences. For example, allowing customers to subscribe to your company newsletter or for holiday news. 

{% hint style="success" %}
Zaius does not require customers to be subscribed to a List to receive emails.
{% endhint %}

{% tabs %}
{% tab title="Single List" %}
```javascript
// subscribe johnny@zaius.com to newsletter list
zaius.subscribe({list_id: 'newsletter', email: 'johnny@zaius.com'});
```

```javascript
// unsubscribe johnny@zaius.com from newsletter list
zaius.unsubscribe({list_id: 'newsletter', email: 'johnny@zaius.com'});
```
{% endtab %}

{% tab title="Multiple Lists" %}
```javascript
// subscribe johnny@zaius.com to three lists at once
zaius.subscribe({
  list_id: ["newsletter", "promotion", "product_update"], 
  email: "johnny@zaius.com"
});
```

```javascript
// unsubscribe johnny@zaius.com from multiple lists at once
zaius.unsubscribe({
  list_id: ["newsletter", "product_update"], 
  email: "johnny@zaius.com"
});
```
{% endtab %}

{% tab title="Including Additional Fields" %}
```javascript
zaius.subscribe({
  // subscribe Johnny to all lists
  
  list_id: ["newsletter", "promotion", "product_update"],
  email: "johnny@zaius.com",
  
  // update Johnny's record to include his full name
  first_name: "Johnny",
  last_name: "Zaius",
  
  // store information on the subscribe events
  event_custom_field: "my custom value",
  custom_number_field: 123
  
});

// zaius.unsubscribe also fully supports this syntax.
```
{% endtab %}
{% endtabs %}

## Events

Zaius generates events automatically for the purposes of analytics and auditing. The events are structured as follows:

| Event Type | Event Action | List ID | Date / Time |
| :--- | :--- | :--- | :--- |
| list | subscribe | newsletter | 123456 |
| list | unsubscribe | newsletter | 123456 |



