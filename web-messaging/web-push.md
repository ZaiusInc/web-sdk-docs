# Web Push

## Advanced Initialization

If you want to create your own web push subscribe experience, Zaius supports custom initialization options.

To manually handle Web Push initialization \(instead of automatically initializing\) go to step 5 of Web Push wizard within Zaius: Account Settings -&gt; Integrations -&gt; Web Push

{% hint style="info" %}
Integration of web push will not be marked as "live" but should be configured.
{% endhint %}

### Display Subscription Modal on Specific Page

In JavaScript on your website, AFTER Zaius is initialized, perform any JS logic and call this when you are ready to show the subscription UI: 

```javascript
{
    "codes": [{
        "code": "zaius.dispatch('webPush', 'initialize', {websiteID: ''})",
        "language": "javascript",
        "name": "Show Subscribe"
    }]
}
```

{% hint style="warning" %}
`websiteID` is the name given in the web push subscribe setup, NOT your tracker\_id
{% endhint %}

### Custom Initialization

In JavaScript on website, AFTER Zaius is initialized, perform any JS logic and call this when you are ready to show the subscription UI:

```javascript
zaius.dispatch('webPush', 'initialize', 
               {websiteID: '<ZAIUS_WEBSITE_ID>', 
                subscribeUI: {enabled: false}}
              );

//Then, check the subscription status before showing your subscription UI:
zaius.dispatch('webPush', 'subscriptionStatus', function(status, token) {
  if (status !== 'subscribed' && status !== 'denied') {
    // show subscribe UI
  }
});

//Finally, when you want the browser to ask the user to allow push notifications call:
zaius.dispatch('webPush', 'askToSubscribe');
```

