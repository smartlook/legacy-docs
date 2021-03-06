---
title: "GDPR"
subtitle: "Record user information about EU visitors."
description: "Depending on content you record you need your user’s consent."
---

Make sure you enabled the corresponding project settings before using this API.
{: .callout .callout-warning }

## Verify user consent

Read more about [GDPR](https://www.smartlook.com/help/gdpr/){:target="_blank"} in our HELP section. Once the user gave consent, you can use this API. The code below needs to be adjusted based on the user's answer.

At Smartlook we use a pop-up window to ask for user consent. You should implement a similar solution on your site.

![user consent](/assets/img/docs/web/gdpr/consent.png)

Verify if a visitor gave their consent or not:

```js
<script>
  smartlook(function() {
    console.log(smartlook.consent.api)
    console.log(smartlook.consent.forms)
    console.log(smartlook.consent.ip)
  });
</script>
```

There are 3 possible values that you can see in the console:

1. `true` if user agreed and provided consent
2. `false` if user refused to provide consent
3. `null` if user was not asked for consent yet

## Form inputs

User consented to have their form inputs recorded.

```js
<script>
  // in this variable inser your consent
  var consentText = 'Here goes consent text from your website.';

  // choose only one variable
  var clientDecision = true; // if user agreed and provided consent
  var clientDecision = false; // if user refused to provide consent

  smartlook('consentForms', clientDecision ? consentText : false);
</script>
```

## IP address

User consented to have their IP address recorded.

```js
<script>
  // in this variable inser your consent
  var consentText = 'Here goes consent text from your website.';

  // choose only one variable
  var clientDecision = true; // if user agreed and provided consent
  var clientDecision = false; // if user refused to provide consent

  smartlook('consentIP', clientDecision ? consentText : false);
</script>
```

## Identify user via API

User consented to being identified via the API.

```js
<script>
  // in this variable inser your consent
  var consentText = 'Here goes consent text from your website.';

  // choose only one variable
  var clientDecision = true; // if user agreed and provided consent
  var clientDecision = false; // if user refused to provide consent

  smartlook('consentAPI', clientDecision ? consentText : false);
</script>
```

## GDPR safe data

You can add atribute `data-recording-gdpr-safe` to any element that is safe and its numerical data (numbers, prices) are not sensitive.

```html
<p data-recording-gdpr-safe>
  Tesla Model X price is $80,700.
</p>
```
