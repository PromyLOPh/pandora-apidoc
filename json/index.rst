JSON API v5
===========

The current JSON API version is 5. Two different endpoints are available:

- http://tuner.pandora.com/services/json/
- https://tuner.pandora.com/services/json/

- http://internal-tuner.pandora.com/services/json/
- https://internal-tuner.pandora.com/services/json/

.. _bodyenc:

Unless noted otherwise JSON-encoded requests sent by the client within the HTTP
POST body are encrypted using Blowfish ECB and converted to hexadecimal
notation.

These URL parameters must be appended to the endpoint above if available:

==========  ===========
Name        Description
==========  ===========
method      Method name
auth_token  User auth token if available, partner auth token or empty if neither is known yet.
partner_id  Partner id obtained by :ref:`auth-partnerLogin` or empty
user_id     User id as obtained by :ref:`auth-userLogin` or empty
==========  ===========

For instance when calling :ref:`auth-userLogin` two parameters are known:
method and partner_id. The URL in this case would be
``http://tuner.pandora.com/services/json/?method=auth.userLogin&partner_id=123``.
Make sure you URL encode the parameter’s values.

The following values must be present in every JSON request object (if available): 

.. _synctime:

=============  ======  ===========
Name           Type    Description
=============  ======  ===========
userAuthToken  string  User auth token, see :ref:`auth-userLogin`
syncTime       int     Synchonized time. Calculation: current time + (time of :ref:`auth-partnerLogin` request – syncTime from :ref:`auth-partnerLogin` response). This is a protection against replay-attacks.
=============  ======  ===========

Every response includes the key ``stat`` which indicates success (``ok``) or
failure (``fail``) of the resquest. Failed requests contain an error code and
message whereas successful requests carry actual response data in the key
``result``:

.. code:: json

    {
        "stat": "ok",
        "result": {
        }
    }

.. code:: json

    {
        "stat": "fail",
        "message": "An unexpected error occurred",
        "code": 1008
    }

.. toctree::

   authentication
   stations
   play
   bookmarks
   account
   methods
   errorcodes
   implementations

.. toctree::
   :hidden:

   partners

