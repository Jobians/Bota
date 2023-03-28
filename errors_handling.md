# Errors Handling

We have two types of errors, Bota error (Server error) and Telegram error

## Bota Error

This error can be handle in two ways:
1. By setting your telegram id in the bot setting tab

2. By creating `!` command with the following example code:
```php
<?php
// "!" error command example code
$admin_id = 1350180828;
$Bot->sendMessage([
    "chat_id" => $admin_id,
    "text" => $error
]);
```
Some pre defined veriable that will be present in `!` error command when server error occur:

- `$command`: The command which the error occur in.
- `$errline`: The line number where the error occur.
- `$error`: The full error message.


## Telegram Error

This error can only be handled by setting up your telegram id in the bot setting tab. 

![](</.gitbook/assets/IMG_20230328_101347_536.jpg>)

After setting your telegram id, bot will automatically send all telegram errors in your pm only.

### Here's the full list:  

- `BadRequestException` (400)
- `UnauthorizedException` (401)
- `ForbiddenException` (403)
- `NotFoundException` (404)
- `MethodNotAllowedException` (405)
- `ConflictException` (409)
- `RequestEntityTooLargeException` (413) (probably thrown only when sending files/video/photos etc.)  
- `TooManyRequestsException` (429)
- `BadGatewayException` (502) (yes, sometimes it happens)

These can be treated like the main one.
