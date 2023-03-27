# Setting up the Bot Panel

The Bot Panel is a tool that allows you to manage the settings for your bot. To set up the Bot Panel, you will need to create a `panel.json` command with the following example information:

## `panel.json` command format

```json
{
    "description": "General bot informations",
    "button_title": "Save Changes",
    "fields": [
        {
            "name": "bot_name",
            "title": "Bot Name",
            "type": "text",
            "value": "Test Bot",
            "description": "Your Bot Name."
        },
        {
            "name": "last_name",
            "title": "Last Name",
            "type": "text",
            "value": "",
            "description": "Your last name."
        },
        {
            "name": "email",
            "title": "Email",
            "type": "email",
            "value": "jobianstechie@gmail.com",
            "description": "Your email address."
        }
    ]
}
```

### `description`

The `description` field is a short description of the bot settings that will be managed in the Bot Panel.

### `button_title`

The `button_title` field is the text that will be displayed on the button used to save changes made to the bot settings.

### `fields`

The `fields` field is an array of objects, each of which represents a field in the Bot Panel. Each object has the following fields:

- `name`: A unique name for the field.
- `title`: The title of the field that will be displayed to the user.
- `type`: The type of field. Currently, only `text` and `email` are supported.
- `value`: The default value of the field.
- `description`: A description of the field that will be displayed to the user.

## Using the Bot Panel

To use the Bot Panel, simply include the `panel.json` file in your bot's project directory. Then, load the file using your preferred method of reading JSON files in your programming language. Finally, render the fields in the file to a web page, and allow users to edit the values of the fields. When the user clicks the save button, save the values of the fields to a database or configuration file.
