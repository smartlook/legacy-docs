---
title: "Identify visitor"
subtitle: "Display detailed visitor information in the dashboard."
description: "In addition to basic info shown in dashboard, you can also identify your users with their email, name or any other property."
---

**Developer needed:** The `identify` method requires you or *your developer* to propagate information from your service. This method is called from your visitor's browser, therefore any information you want to associate with your visitor needs to be part of your webpage.
{: .callout .callout-warning }

## Visitor information

Below is the simplest usage of the `identify` method. The example assumes there is a `user_id` variable identifying your visitor. The JavaScript code you need to insert in your is simply,

```js
<script>
  smartlook('identify', user_id);
</script>
```

**`user_id`** is a unique number or string used to identify your user.

The next example assumes you are using a template used for rendering the final HTML in which you can pass information about the current visitor. Pairing your visitor with your internal identifier enables you to find this user in Smartlook by this identifier.

{% include component/tables/docs/{{ page.title | slugify }}/visitor-information.html %}

Here is an example in **PHP**.

```php
echo "<script>";
echo "smartlook('identify', '{$user->id}');";
echo "</script>";
```

That will generate the following JavaScript code on the page:

```js
<script>
  smartlook('identify', '123');
</script>
```

## More visitor details

There is no limit to what you can display in the dashboard. It can be the user's **name** or **email**, or also what **package** the user paid for, in what **currency**, and what the **price** was.

The third parameter of the `identify` method is optional. It is expected to be an object. The keys of this object are entirely up to you, as well as all of the values.

Feel free to modify the code and expand it to your needs as you can see in the example below.

```js
<script>
  smartlook('identify', uid, {
    "name": "John Doe",
    "email": "john.doe@example.com",
    "package": "Premium",
    "currency": "USD",
    "price": 150
  });
</script>
```

## Anonymize user

You can anonymize the previously identified user by calling

```js
<script>
  smartlook('anonymize');
</script>
```

A new visitor with a new session will be created.
This method is useful to call when multiple people are using the same browser (typically after logout).

## Static site usage

The `identify` method should always be called *after* the Smartlook Web SDK is initialized.

If you are integrating the Smartlook Web SDK within the `<head></head>` section of your static site, the actual `identify` call should be just before the closing `</body>` tag.

You need to propagate your data into the HTML that is sent to your client. `identify` is called on the client and your data can only be passed to Smartlook when it's part of the HTML.
