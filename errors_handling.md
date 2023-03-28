# Errors Handling

We have two types of errors, Bota error (Server error) and Telegram error






## Bota Error

The settings debug parameter just creates this error handler:  
```php
$Bot->addErrorHandler(function (Throwable $e) use ($Bot) {
    $Bot->debug( (string) $e );
});
```

## Telegram Error

Telegram Exceptions thrown by NovaGram are `skrtdev\Telegram\Exceptions`, but sometimes they are more speficic Exceptions that extend the main one, according to `error_code` number. Here's the full list:  

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
