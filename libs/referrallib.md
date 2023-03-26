# ReferralLib

Use this Lib for referral system and tracking.

### Available ReferralLib Functions
   * [track](#track)
   * [getLink](#getLink)
   * [getReferredBy](#getReferredBy)
   * [getRefCount](#getRefCount)
   * [getRefList](#getRefList)
   * [getTopList](#getTopList)
   * [getUsersList](#getUsersList)
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

// output https://t.me/botname?start=ref01234567
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
$myref = $Libs->ReferralLib->getReferredBy();
if 
$User->sendMessage("Your referral link is: $mylink");
```
