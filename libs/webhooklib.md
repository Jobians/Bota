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

Example:
```php
<?php
$Libs->ResourcesLib->userRes("balance");
```
