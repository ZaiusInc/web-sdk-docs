# Web Modals / Embeds

To manually display web content based on your own criteria, Zaius provides an SDK method for your development team to utilize.

Using this snippet, you can trigger a modal in custom scenarios; e.g. when your customer adds an item to cart or logs in.

```javascript
zaius.dispatch(
'web', 
'showContent', {
  contentId: '<insert_content_id>', 
  target: {
    selector: '<insert css selector>', // empty string for modals 
    position: 'modal' // modal | before | after | inside | replace
  }
});
```

{% hint style="info" %}
A campaign must be created and launched within Zaius before this snippet will work.
{% endhint %}

  


