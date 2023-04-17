# Variables

Here's a list of predefined variables available now:

- `$update` - contains the incoming update from Telegram
- `$message` - contains the message object from the update, if it exists
- `$callback_query` - contains the callback query object from the update, if it exists
- `$chat` - contains the chat object associated with the message or callback query
- `$Chat` - same as `$chat`, but with a capitalized first letter (possibly a typo)
- `$first_name` - contains the first name of the user associated with the chat
- `$chat_id` - contains the unique identifier of the chat
- `$User` - contains the user object associated with the message or callback query
- `$user` - same as `$User`, but with a lowercase first letter (possibly a typo)
- `$user_id` - contains the unique identifier of the user
- `$text` - contains the text message or callback data, if it exists
- `$callback_id` - contains the unique identifier of the callback query
- `$message_id` - contains the unique identifier of the message

You can use these variables to access information about the incoming message or callback query, such as the chat ID, user ID, and message text. You can also use these variables to send a response back to the user, for example, by using the `$chat_id` variable to send a message to the chat.
