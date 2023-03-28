# Updates Handling

Bota makes it easy for you to handle other telegram updates except `Message` update which is already handled via command, to handle different kinds of updates, you can put your code in the `*` command.

There is an handler for each property of the `Update` object

- `onEditedMessage`  
- `onChannelPost`  
- `onEditedChannelPost`  
- `onInlineQuery`  
- `onChosenInlineResult`  
- `onShippingQuery`  
- `onPreCheckoutQuery`  
- `onPoll`  
- `onPollAnswer`  
- `onMyChatMember`  
- `onChatMember`  

### `onNewChatMember`

Handles users being added to groups. As the bot can also be added to groups, you can use [onNewGroup handler](#onnewgroup).  
This handles only other users by default, if you want to get bots too, just pass `true` in the 2nd argument.  

```php
$Bot->onNewChatMember(function (Chat $Chat, User $User, User $adder) {
    $Chat->sendMessage("Welcome, {$User->getMention()}");
});

// if you want to handle bots too:
$Bot->onNewChatMember(function (Chat $Chat, User $User, User $adder) {
    $Chat->sendMessage("Welcome, {$User->getMention()}");
}), true);
```

### `onNewGroup`

Handles bot being added to groups.  
As you already know that it is your bot, there is no `$User` argument.  
Let's compare this method with `onNewChatMember` usage:  


```php
$Bot->onNewChatMember(function (Chat $Chat, User $User, User $adder) use ($Bot) {
    if($User->id === $Bot->id){
        $Chat->sendMessage("Thanks {$adder->getMention()} for adding me to this group!");
    }
}), true);
```
```php
$Bot->onNewGroup(function (Chat $Chat, User $adder) {
    $Chat->sendMessage("Thanks {$adder->getMention()} for adding me to this group!");
});
```
