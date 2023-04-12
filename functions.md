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
runAfter function is used to run command after specific amount of time, we only support from 1 to 44640 minutes.

```php
// handle another command
$Bot->handleCommand("/amount");

// handle another command with options
$Bot->handleCommand("/amount", ['options' => ['user_id' => 0123456789,'currency' => 'TRX']]);

// in second command /amount:
$Bot->sendMessage(["chat_id" => $options->user_id, "text" => "You will deposit: " . $options->currency]);
```
