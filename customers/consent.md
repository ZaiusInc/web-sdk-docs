---
description: Set a customer's consent for receiving marketing communication.
---

# Consent

{% hint style="danger" %}
Users who are opted-out cannot receive marketing messages from Zaius. Only transactional messages will be received by these users.
{% endhint %}

## Opt-In

```javascript
zaius.subscribe({list_id: 'zaius_all', email: 'johnny@zaius.com'});
```

## Opt-out

```javascript
zaius.unsubscribe({list_id: 'zaius_all', email: 'johnny@zaius.com'});
```



