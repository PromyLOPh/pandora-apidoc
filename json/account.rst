Account
=======


.. index::
   pair: method; user.validateUsername

.. _user-validateUsername:

Validate username
-----------------

:Method: user.validateUsername

This method can be used before authenticating a user with
:ref:`auth-userLogin`, but requires a valid :ref:`auth-partnerLogin`.

.. csv-table::
   :header: Name,Type,Description

   username,string,

.. csv-table::
   :header: Name,Type,Description

   isValid,boolean,
   isUnique,boolean,


.. index::
   pair: method; user.createUser

.. _user-createUser:

Create new account
------------------

:Method: user.createUser

.. csv-table::
   :header: Name,Type,Description

    username,string,
    password,string,
    gender,string,
    birthYear,int,
    zipCode,int,
    emailOptIn,boolean,
    countryCode,string,
    accountType,string,``registered``,
    registeredType,string,``user``,
    includePandoraOneInfo,boolean,
    includeAccountMessage,boolean,
    returnCollectTrackLifetimeStats,boolean,
    returnIsSubscriber,boolean,
    xplatformAdCapable,boolean,
    includeFacebook,boolean,
    includeGoogleplay,boolean,
    includeShowUserRecommendations,boolean,
    includeAdvertiserAttributes,boolean,

.. TODO response?

.. _settingkeys:

Settings
--------

The following settings are currently read/writeable:

.. csv-table::
   :header: Name,Type,Description

   gender,string,``Male`` or ``Female``
   birthYear,int,
   zipCode,string,
   isProfilePrivate,boolean,
   enableComments,boolean,
   emailOptIn,boolean,
   emailComments,boolean,
   emailNewFollowers,boolean,
   isExplicitContentFilterEnabled,boolean,
   isExplicitContentFilterPINProtected,boolean,
   currentUsername,string,
   currentPassword,string,
   newUsername,string,
   newPassword,string,
   facebookAutoShareEnabled,boolean,
   autoShareTrackPlay,boolean,
   autoShareLikes,boolean,
   autoShareFollows,boolean,
   facebookSettingChecksum,boolean,
   userInitiatedChange,boolean,


.. index::
   pair: method; user.getSettings

.. _user-getSettings:

Retrieve
^^^^^^^^

:Method: user.getSettings

.. csv-table::
   :header: Name,Type,Description

   includeFacebook,boolean,

See :ref:`settingkeys` for return values.


.. index::
   pair: method; user.changeSettings

.. _user-changeSettings:

Modify
^^^^^^

:Method: user.changeSettings

.. csv-table::
   :header: Name,Type,Description

   includeFacebook,boolean,

Additionally keys listed in :ref:`settingkeys` are permitted in the request
body.

.. TODO response?


.. index::
   pair: method; user.emailPassword

.. _user-emailPassword:

Recover password
----------------

:Method: user.emailPassword

.. csv-table::
   :header: Name,Type,Description

   username,string,

.. TODO response?


.. index::
   pair: method; user.canSubscribe

.. _user-canSubscribe:

Get subscriber status
---------------------

:Method: user.canSubscribe

Returns whether a user is subscribed or if they can subscribe to Pandora One.
Can be useful to determine which :ref:`Partner password<partners>` to use.

.. csv-table::
   :header: Name,Type,Description

    iapVendor,string,(optional)

.. csv-table::
   :header: Name,Type,Description

   canSubscribe,boolean,false if user is a Pandora One subscriber
   isSubscriber,boolean,true if user is a Pandora One Subscriber

.. code:: json

    {
        "stat": "ok",
         "result": {
              "canSubscribe": false,
              "isSubscriber": true
         }
     }


.. index::
   pair: method; user.getUsageInfo

.. _user-getUsageInfo:

Usage info
----------

:Method: user.getUsageInfo

The request has no parameters.

.. csv-table::
   :header: Name,Type,Description

    accountMonthlyListening,int,
    deviceMonthlyListening,int,
    monthlyCapHours,int,
    monthlyCapWarningPercent,int,
    monthlyCapWarningRepeatPercent,int,
    isMonthlyPayer,bool,
    isCapped,bool,
    listeningTimestamp,int,

.. code:: json

    {
        "stat": "ok",
        "result": {
            "monthlyCapWarningRepeatPercent": 10,
            "monthlyCapHours": 320,
            "deviceMonthlyListening": 0,
            "isMonthlyPayer": false,
            "isCapped": false,
            "monthlyCapWarningPercent": 85,
            "accountMonthlyListening": 0
        }
    }

