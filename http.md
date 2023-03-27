# HTTP Class

The HTTP class provides a simple way to make HTTP requests and send emails via a RESTful API.

## Usage

To use the HTTP class, follow these steps:

1. Create an instance of the HTTP class:
    ```php
    $http = new HTTP();
    ```

2. Make a GET request:
    ```php
    $url = 'https://example.com/api/get';
    $headers = [
        'Authorization: Bearer myToken'
    ];
    $response = $http->get($url, $headers);
    ```

3. Make a POST request:
    ```php
    $url = 'https://example.com/api/post';
    $data = [
        'name' => 'John Doe',
        'email' => 'johndoe@example.com'
    ];
    $headers = [
        'Authorization: Bearer myToken'
    ];
    $response = $http->post($url, $data, $headers);
    ```

4. Send an email:
    ```php
    $data = [
        'to' => 'recipient@example.com',
        'subject' => 'Hello',
        'message' => 'This is a test email'
    ];
    $response = $http->sendMail($data);
    ```

## Methods

### `post($url, $data = [], $headers = [])`

Sends a POST request to the specified URL.

#### Parameters:

- `$url` (string): The URL to send the request to.
- `$data` (array|string): The data to send with the request.
- `$headers` (array): An array of headers to send with the request.

#### Returns:

- The response from the server.

### `get($url, $headers = [])`

Sends a GET request to the specified URL.

#### Parameters:

- `$url` (string): The URL to send the request to.
- `$headers` (array): An array of headers to send with the request.

#### Returns:

- The response from the server.

### `sendMail($data)`

Sends an email using the specified data.

#### Parameters:

- `$data` (array): An array of data required to send the email.

#### Returns:

- The response from the server.
