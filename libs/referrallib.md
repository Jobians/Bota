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
$Bot->runCommand("/deposit");

// you can add other code for the /start command from here
```
