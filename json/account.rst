Account
=======

.. _settingkeys:

Available settings
------------------

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

.. _user-getSettings:

Retrieve settings
-----------------

:Method: user.getSettings

.. csv-table::
   :header: Name,Type,Description

   includeFacebook,boolean,

See :ref:`settingkeys` for return values.

.. _user-changeSettings:

Change settings
---------------

:Method: user.changeSettings

.. csv-table::
   :header: Name,Type,Description

   includeFacebook,boolean,

Additionally keys listed in :ref:`settingkeys` are permitted in the request
body.

.. TODO: response?

