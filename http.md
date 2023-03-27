# HTTP Request

The HTTP class provides a simple way to make HTTP requests and send emails via a RESTful API.

## Usage

To use the HTTP class, follow these steps:

1. Make a GET request:
    ```php
    $url = 'https://example.com/api/get';
    $headers = [
        'Authorization: Bearer myToken'
    ];
    $response = $HTTP->get($url, $headers);
    ```

2. Make a POST request:
    ```php
    $url = 'https://example.com/api/post';
    $data = [
        'name' => 'John Doe',
        'email' => 'johndoe@example.com'
    ];
    $headers = [
        'Authorization: Bearer myToken'
    ];
    $response = $HTTP->post($url, $data, $headers);
    ```

3. Send an email:
    ```php
    $data = [
        'sender' => 'yourgmail@gmail.com',
        'password' => 'your_gmail_app_password',
        'recipient' => 'recipient@example.com',
        'subject' => 'Hello',
        'message' => 'This is a test email'
    ];
    $response = $HTTP->sendMail($data);
    ```

## Methods

### `post($url, $data, $headers = [])`

Sends a POST request to the specified URL.

#### Parameters:

- `$url` (string): The URL to send the request to.
- `$data` (array): The data to send with the request.
- `$headers` (array) (optional): An array of headers to send with the request.

#### Returns:

- The response from the server.

### `get($url, $headers = [])`

Sends a GET request to the specified URL.

#### Parameters:

- `$url` (string): The URL to send the request to.
- `$headers` (array) (optional): An array of headers to send with the request.

#### Returns:

- The response from the server.

### `sendMail($data)`

Sends an email using the specified data.

#### Parameters:

- `$data` (array): An array of data required to send the email.

#### Returns:

- The response from the server.
