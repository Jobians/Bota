# Functions

Coding in Bota, you can use all the usual PHP functions except file_get_contents() and eval()

### Available Functions
   * [runCommand](#runcommand)
   * [handleCommand](#handlecommand)
   * [setProperty](#setproperty)
   * [getProperty](#getproperty)


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

