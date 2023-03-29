# Updates Handling

Bota makes it easy for you to handle other telegram updates except `Message` update which is already handled via command, to handle different kinds of updates, you can put your code in the `*` command.

Simple example how to handle `edited_message` update

```php
<?php
// for * command
if ($update) {
    if (isset($update->edited_message)) {
        $chat_id = $update->edited_message->chat->id;
        $message_id = $update->edited_message->message_id;
        $Bot->sendMessage([
            "chat_id" => $chat_id,
            "text" => "😅 Caught it, you edited this message now.",
            "reply_to_message_id" => $message_id
        ]);
    }
}
```
