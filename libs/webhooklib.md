# WebhookLib

The WebhookLib has one method named `getUrl()` that returns a webhook URL based on the provided parameters.

### Usage
Here is the usage documentation for the `getUrl()` method:

```php
<?php
$Libs->WebhookLib->getUrl($command, $user_id, $options, $redirect_to);
```
`$command`: The name of the webhook command to execute.<br>
`$user_id`: The ID of the user who triggered the webhook.<br>
`$options` (optional): An array of additional options to pass to the webhook.<br>
`$redirect_to` (optional): A URL to redirect the user to after the webhook is executed.

### Example 1:
Get webhook url for the current user without $options and $redirect_to parameters

```php
<?php
$webhook = $Libs->WebhookLib->getUrl("/onWebhook", $user_id);
$User->sendMessage($webhook);
```

### Example 2:
Full usage example of this webhook lib

```php
<?php
// set command and user_id
$command = "/onWebhook";
$user_id = $user_id; // for current user or replace it with the another user telegram id

// build URL with options and redirect_to parameters
$options = array('category' => 'tech');
$redirect_to = "https://www.google.com/search";

$webhook = $Libs->WebhookLib->getUrl($command, $user_id, $options, $redirect_to);
$User->sendMessage($webhook);
```

On command `/onWebhook` we can get posted content from the webhook
```php
<?php
// get the user_id to send message from the webhook

```


Webhooks can be with GET and POST methods only. All passed data contains on content variable
