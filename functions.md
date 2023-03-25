# Functions

Coding in Bota, you can use all the usual PHP functions except file_get_contents() and eval()

### Available Functions
   * [runCommand](#runCommand)
   * [setProperty](#setProperty)
   * [getProperty](#getProperty)
   * [answerCallbackQuery](#answercallbackquery)
   * [editMessageText](#editmessagetext)
   * [sendChatAction](#sendchataction)
   * [getUserProfilePhotos](#getuserprofilephotos)
   * [getUsernameDC](#getusernamedc)


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

