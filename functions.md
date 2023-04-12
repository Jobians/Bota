# Functions

Coding in Bota, you can use all the usual PHP functions except file_get_contents() and eval()

### Available Functions
   * [runCommand](#runcommand)
   * [handleCommand](#handlecommand)
   * [setProperty](#setproperty)
   * [getProperty](#getproperty)
   * [banChat](#banchat)
   * [unbanChat](#unbanchat)
   * [runAfter](#runafter)


### runCommand
runCommand can be used to run another command.  

```php
// run other command
$Bot->runCommand("/deposit");

// run other command with options
$Bot->runCommand("/deposit", ['options' => ['user_id' => 0123456789,'currency' => 'TRX']]);

// in second command /deposit:
$Bot->sendMessage(["chat_id" => $options->user_id, "text" => "You will deposit: " . $options->currency]);
```

### handleCommand
handleCommand AKA waitForAnswer can be use to wait for user response or answer 

```php
// handle another command
$Bot->handleCommand("/amount");

// handle another command with options
$Bot->handleCommand("/amount", ['options' => ['user_id' => 0123456789,'currency' => 'TRX']]);

// in second command /amount:
$Bot->sendMessage(["chat_id" => $options->user_id, "text" => "You will deposit: " . $options->currency]);
```

### setProperty
setProperty function can be used to set property with name for bot.

```php
// main class
$Bot->setProperty($chat_id, "name", "value"); // set property for the specific user

// User object
$User->conversation("name", "value"); // set property for the current user
```


### getProperty
getProperty function can be use to read property with name. Name is case sensitive.
```php
// main class
$Bot->getProperty($chat_id, "name"); // get property value for the specific user

// User object
$User->conversation("name"); // get property value for the current user
```


### banChat
Use this function to ban chat id or user in your bot.
```php
<?php
$Bot->banChat($chat_id);
```
You can also pass reason message to send to the banned chat id (optional)
```php
<?php
$reason = "Sorry, you have been banned for using multiple account";
$Bot->banChat($chat_id, $reason);
```


### unbanChat
Use this function to unban banned chat id in your bot.
```php
<?php
$Bot->unbanChat($chat_id);
```

### runAfter
runAfter method is used to schedule a command to run after a specified number of minutes (1 to 44640). It can be used in bots to automate tasks and execute commands at a later time.

- Parameters

The method takes in a single parameter, `$settings`, which is an array of options that specify the details of the command to be scheduled. The following options are available:

```php
$settings = [
    'command' => '',    // The name of the command to run after the specified number of minutes.
    'minutes' => '',    // The number of minutes after which the command should be run.
    'label' => '',      // (Optional) A label to identify the scheduled task.
    'options' => []     // (Optional) An array of additional options to pass to the command.
];
```

- Usage

```php
$settings = [
    'command' => 'my_command',    // Replace with the name of your command.
    'minutes' => 60,              // Replace with the number of minutes after which the command should run.
    'label' => 'my_label',        // (Optional) Replace with a label to identify the scheduled task.
    'options' => []              // (Optional) Replace with an array of additional options to pass to the command.
];
$id = Bot::addMethod("runAfter", $settings);
if ($id) {
    echo "Command scheduled successfully!";
} else {
    echo "Error scheduling command.";
}
```
