# ReferralLib

Use this Lib for referral system and tracking.

### Available ReferralLib Functions
   * [track](#track)
   * [getLink](#getlink)
   * [getReferredBy](#getreferredby)
   * [getRefCount](#getrefcount)
   * [getRefList](#getreflist)
   * [getTopList](#gettoplist)
   * [getUsersList](#getuserslist)
   * [destroy](#destroy)


### track
Basic function is track. Prefer to call it on /start command, it will start the lib and track users referral:  

```php
<?php
// for /start command
$Libs->ReferralLib->track();

// you can add other code for the /start command from here
```

### getLink
Get Referral link for current user or another user

```php
<?php
// get referral link for the current user
$Libs->ReferralLib->getLink();

// get referral link for the another user
$user_telegramid = 0123456789;
$Libs->ReferralLib->getLink($user_telegramid); // the user must start your bot for this to work

// output eg: https://t.me/botname?start=ref01234567
```

Example:
```php
<?php
$mylink = $Libs->ReferralLib->getLink();
$User->sendMessage("Your referral link is: $mylink");
```

### getReferredBy
Get Referred id for current user or another user

```php
<?php
// get Referred id for the current user
$Libs->ReferralLib->getReferredBy();

// get Referred id for the another user
$user_telegramid = 0123456789;
$Libs->ReferralLib->getReferredBy($user_telegramid); // the user must start your bot for this to work

// output user_id eg: 0123456789 if the user is referred else return null
```

Example:
```php
<?php
$referer = $Libs->ReferralLib->getReferredBy();
if ($referer) {
    $User->sendMessage("You was referred by $referer");
} else {
    $User->sendMessage("You was not referred by anyone");
}
```

### getRefCount
Get referral count for current user or another user

```php
<?php
// get referral count for the current user
$Libs->ReferralLib->getRefCount();

// get referral count for the another user
$user_telegramid = 0123456789;
$Libs->ReferralLib->getRefCount($user_telegramid); // the user must start your bot for this to work

// output eg: 2 if the user have referrals else return 0
```

Example:
```php
<?php
$ref_count = $Libs->ReferralLib->getRefCount();
$User->sendMessage("Your referral count is $ref_count");
```

### getRefList
Get referral users list for current user or another user

```php
<?php
// get referral users list for the current user
$Libs->ReferralLib->getRefList();

// get referral users list for the another user
$user_telegramid = 0123456789;
$Libs->ReferralLib->getRefList($user_telegramid); // the user must start your bot for this to work

// output eg: array of user referrals else return null
```

### getTopList
Get top referral list for the bot

```php
<?php
// get top referral list with default limit of 10
$Libs->ReferralLib->getTopList();

// get top referral list with limit of 100
$Libs->ReferralLib->getTopList(100);

// output eg: array of top referrals else return null
```

### getUsersList
Get the list of all user id for the bot, good for broadcast

```php
<?php
// get list of all user id for the bot
$Libs->ReferralLib->getUsersList();

// output eg: array of all user id for the bot else return null
```

### destroy
Use this function if only you want to reset or empty referral lib data for the current bot:  

```php
<?php
$Libs->ReferralLib->destroy();

// it will return true
```
