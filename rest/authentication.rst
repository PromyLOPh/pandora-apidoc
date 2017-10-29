.. _rest-authentication:

==============
Authentication
==============

.. _rest-v1-auth-login:

User Login
==========

:Endpoint: /v1/auth/login

Request
-------
.. code:: json

    {
        "existingAuthToken": null,
        "keepLoggedIn": true,
        "password": "secretpassword",
        "username": "email@example.com"
    }

.. csv-table::
    :header: Name,Type,Description

    username,string,User's username
    password,string,User's password

Response
--------
.. code:: json

    {
        "activeVxRewards": [],
        "adkv": {},
        "allowProfileComments": false,
        "artistAudioMessagesEnabled": false,
        "artistPromoEmailsEnabled": false,
        "authToken": "dGhpcyBpcyBqdXN0IGFuIGV4YW1wbGUgY29kZQo=",
        "birthYear": 1920,
        "config": {
            "branding": "PandoraPlus",
            "dailySkipLimit": 60,
            "experiments": [
                123,
                456
            ],
            "flags": [
                "noAds",
                "adFreeSkip",
                "adFreeReplay",
                "noSmartConversion",
                "disableNonAdPageTimeout",
                "highQualityStreamingAvailable",
                "replaysEnabled"
            ],
            "inactivityTimeout": 28800,
            "monthlyListeningCapHours": 320,
            "stationSkipLimit": 6
        },
        "emailOptOut": true,
        "explicitContentFilterEnabled": false,
        "gender": "FEMALE",
        "highQualityStreamingEnabled": true,
        "isNew": false,
        "listenerId": "12345",
        "listenerToken": "GFuIGV4YW1wbGUgY29kZQodGhpcyBpcyBqdXN0I",
        "minor": false,
        "notifyOnComment": true,
        "notifyOnFollow": true,
        "profilePrivate": true,
        "seenEducation": true,
        "smartConversionAdUrl": "https://adserver.pandora.com/...",
        "smartConversionDisabled": true,
        "smartConversionTimeoutMillis": 5000,
        "stationCount": 13,
        "username": "email@example.com",
        "webClientVersion": "0.48.0",
        "webname": "user",
        "zipCode": "12345"
    }

.. csv-table::
    :header: Name,Type,Description

    authToken,string,See :ref:`rest-auth-token`
