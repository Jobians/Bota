# ResourcesLib

Use this Lib to manage any resources in bot.

### Available ResourcesLib Methods
   * [userRes](#userres)
   * [anotherChatRes](#anotherchatres)
   * [value](#value)
   * [set](#set)
   * [add](#add)
   * [have](#have)
   * [remove](#remove)


### userRes
The `userRes()` method is used to set the `type` of a user's resource for the current user.

```php
<?php
$Libs->$ResourcesLib->userRes($type);
```
`$type` (string): The type of resource.

Example:
```php
<?php
$Libs->ResourcesLib->userRes("balance");
```

### anotherChatRes
The `anotherChatRes()` method is used to set the `user_id` and `type` of another user's resource.

```php
<?php
$Libs->ResourcesLib->anotherChatRes($type, $user_id);
```
`$type` (string): The type of resource.<br>
`$user_id` (int): The ID of the user.

Example:
```php
<?php
$Libs->ResourcesLib->anotherChatRes("balance", 0123456789);
```

### value
The `value()` method returns the current value of a user's resource.

```php
<?php
// get resources value for the current user
$Libs->ResourcesLib->userRes($type)->value();

// get resources value for another user
$Libs->ResourcesLib->anotherChatRes($type, $user_id)->value();
```


Example:
```php
<?php
$balance = $Libs->ResourcesLib->userRes("balance")->value();
$User->sendMessage("Your available balance is: $balance USD");
```

### set
The `set()` method sets the value of a user's resource.

```php
<?php
// set resources value for the current user
$Libs->ResourcesLib->userRes($type)->set($amount);

// set resources value for another user
$Libs->ResourcesLib->anotherChatRes($type, $user_id)->set($amount);
```
`$amount` (int): The value to set.


Example:
```php
<?php
$amount = 100;
$Libs->ResourcesLib->userRes("balance")->set($amount);
$User->sendMessage("Your balance is set to: $amount USD");
```

### add
The `add()` method adds a value to a user's resource.

```php
<?php
// add value to a user's resource for the current user
$Libs->ResourcesLib->userRes($type)->add($amount);

// add value to a user's resource for another user
$Libs->ResourcesLib->anotherChatRes($type, $user_id)->add($amount);
```
`$amount` (int): The value to set.


Example:
```php
<?php
$amount = 2;
$Libs->ResourcesLib->userRes("balance")->add($amount);
$User->sendMessage("You have received: $amount USD");
```

### have
The `have()` method checks if a user has enough resources.

```php
<?php
// check for the current user
$Libs->ResourcesLib->userRes($type)->have($amount);

// check for another user
$Libs->ResourcesLib->anotherChatRes($type, $user_id)->have($amount);

// If it is, the method returns true. If it is not, the method returns false.
```
`$amount` (int): The value to set.


Example:
```php
<?php
$amount = 50;
$check = $Libs->ResourcesLib->userRes("balance")->have($amount);
$User->sendMessage("Your balance is set to: $amount USD");
```
