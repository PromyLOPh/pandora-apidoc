.. _authentication:

Authentication
==============

Authentication is divided into two steps: Partner and user login.

.. _auth-partnerLogin:

Partner login
-------------

:Method: auth.partnerLogin

This request additionally serves as API version validation, time
synchronization and endpoint detection and *must* be sent over a TLS-encrypted
link. The POST body however is :ref:`not encrypted <bodyenc>`.

.. csv-table::
    :header: Name,Type,Description

    username,string,See :ref:`partners`
    password,string,See :ref:`partners`
    deviceModel,string,See :ref:`partners`
    version,string,"Current version number, “5”."
    includeUrls,boolean,
    returnDeviceType,boolean,
    returnUpdatePromptVersions,boolean,

.. code:: json

    {
        "username": "pandora one",
        "password": "TVCKIBGS9AO9TSYLNNFUML0743LH82D",
        "deviceModel": "D01",
        "version": "5"
    }

syncTime is used to calculate the server time, see :ref:`synctime`. partnerId
and authToken are required to procceed with user authentication.

================  =======  ===========
Name              Type     Description
================  =======  ===========
syncTime          string   Hex-encoded, encrypted server time. Decrypt with password from :ref:`partners` and skip first four bytes of garbage.
partnerAuthToken  string
partnerId         string
================  =======  ===========

.. code:: json

    {
        "stat": "ok",
        "result": {
            "syncTime": "6923e263a8c3ac690646146b50065f43",
            "deviceProperties": {
                "videoAdRefreshInterval": 900,
                "videoAdUniqueInterval": 0,
                "adRefreshInterval": 5,
                "videoAdStartInterval": 180
            },
            "partnerAuthToken": "VAzrFQTtsy3BQ3K+3iqFi0WF5HA63B1nFA",
            "partnerId": "42",
            "stationSkipUnit": "hour",
            "urls": {
                "autoComplete": "http://autocomplete.pandora.com/search"
            },
            "stationSkipLimit": 6
        }
    }

====  ============
Code  Description
====  ============
1002  INVALID_PARTNER_LOGIN. Invalid partner credentials. 
====  ============

.. _auth-userLogin:

User login
----------

:Method: auth.userLogin

This request *must* be sent over a TLS-encrypted link. It authenticates the
Pandora user by sending his username, usually his email address, and password
as well as the partnerAuthToken obtained by :ref:`auth-partnerLogin`.

.. TODO: Describe device login.

Additional response data can be requested by setting flags listed below.

.. csv-table::
    :header: Name,Type,Description

    loginType ,string ,“user”
    username ,string ,Username
    password ,string ,User’s password
    partnerAuthToken ,string ,Partner token obtained by :ref:`auth-partnerLogin`
    returnGenreStations ,boolean ,(optional)
    returnCapped ,boolean ,return isCapped parameter (optional)
    includePandoraOneInfo,boolean,(optional)
    includeDemographics,boolean,(optional)
    includeAdAttributes,boolean,(optional)
    returnStationList,boolean,"Return station list, see :ref:`user-getStationList` (optional)"
    includeStationArtUrl,boolean,(optional)
    includeStationSeeds,boolean,(optional)
    includeShuffleInsteadOfQuickMix,boolean,(optional)
    stationArtSize,string,W130H130(optional)
    returnCollectTrackLifetimeStats,boolean,(optional)
    returnIsSubscriber,boolean,(optional)
    xplatformAdCapable,boolean,(optional)
    complimentarySponsorSupported,boolean,(optional)
    includeSubscriptionExpiration,boolean,(optional)
    returnHasUsedTrial,boolean,(optional)
    returnUserstate,boolean,(optional)
    includeAccountMessage,boolean,(optional)
    includeUserWebname,boolean,(optional)
    includeListeningHours,boolean,(optional)
    includeFacebook,boolean,(optional)
    includeTwitter,boolean,(optional)
    includeDailySkipLimit,boolean,(optional)
    includeSkipDelay,boolean,(optional)
    includeGoogleplay,boolean,(optional)
    includeShowUserRecommendations,boolean,(optional)
    includeAdvertiserAttributes,boolean,(optional)


.. code:: json

    {
        "loginType": "user",
        "username": "user@example.com",
        "password": "example",
        "partnerAuthToken": "VAzrFQTtsy3BQ3K+3iqFi0WF5HA63B1nFA",
        "includePandoraOneInfo":true,
        "includeAdAttributes":true,
        "includeSubscriptionExpiration":true,
        "includeStationArtUrl":true,
        "returnStationList":true,
        "returnGenreStations":true,
        "syncTime": 1335777573
    }

The returned userAuthToken is used to authenticate access to other API methods.

.. csv-table::
    :header: Name ,Type ,Description

    isCapped ,boolean ,
    userAuthToken,string,

.. code:: json

    {
        "stat": "ok",
        "result": {
            "stationCreationAdUrl": "http://ad.doubleclick.net/adx/pand.android/prod.createstation;ag=112;gnd=1;zip=23950;genre=0;model=;app=;OS=;dma=560;clean=0;logon=__LOGON__;tile=1;msa=115;st=VA;co=51117;et=0;mc=0;aa=0;hisp=0;hhi=0;u=l*2jedvn446s7ce!ag*112!gnd*1!zip*23950!dma*560!clean*0!logon*__LOGON__!msa*115!st*VA!co*51117!et*0!mc*0!aa*0!hisp*0!hhi*0!genre*0;sz=320x50;ord=__CACHEBUST__",
            "hasAudioAds": true,
            "splashScreenAdUrl": "http://ad.doubleclick.net/pfadx/pand.android/prod.welcome;ag=112;gnd=1;zip=23950;model=;app=;OS=;dma=560;clean=0;hours=1;msa=115;st=VA;co=51117;et=0;mc=0;aa=0;hisp=0;hhi=0;u=l*op4jfgdxmddjk!ag*112!gnd*1!zip*23950!dma*560!clean*0!msa*115!st*VA!co*51117!et*0!mc*0!aa*0!hisp*0!hhi*0!hours*1;sz=320x50;ord=__CACHEBUST__",
            "videoAdUrl": "http://ad.doubleclick.net/pfadx/pand.android/prod.nowplaying;ag=112;gnd=1;zip=23950;dma=560;clean=0;hours=1;app=;index=__INDEX__;msa=115;st=VA;co=51117;et=0;mc=0;aa=0;hisp=0;hhi=0;u=l*2jedvn446s7ce!ag*112!gnd*1!zip*23950!dma*560!clean*0!index*__INDEX__!msa*115!st*VA!co*51117!et*0!mc*0!aa*0!hisp*0!hhi*0!hours*1;sz=442x188;ord=__CACHEBUST__",
            "username": "user@example.com",
            "canListen": true,
            "nowPlayingAdUrl": "http://ad.doubleclick.net/pfadx/pand.android/prod.nowplaying;ag=112;gnd=1;zip=23950;genre=0;station={4};model=;app=;OS=;dma=560;clean=0;hours=1;artist=;interaction=__INTERACTION__;index=__INDEX__;newUser=__AFTERREG__;logon=__LOGON__;msa=115;st=VA;co=51117;et=0;mc=0;aa=0;hisp=0;hhi=0;u=l*op4jfgdxmddjk!ag*112!gnd*1!zip*23950!station*{4}!dma*560!clean*0!index*__INDEX__!newUser*__AFTERREG__!logon*__LOGON__!msa*115!st*VA!co*51117!et*0!mc*0!aa*0!hisp*0!hhi*0!genre*0!interaction*__INTERACTION__!hours*1;sz=320x50;ord=__CACHEBUST__",
            "userId": "272772589",
            "listeningTimeoutMinutes": "180",
            "maxStationsAllowed": 100,
            "listeningTimeoutAlertMsgUri": "/mobile/still_listening.vm",
            "userProfileUrl": "https://www.pandora.com/login?auth_token=XXX&target=%2Fpeople%2FXXX",
            "minimumAdRefreshInterval": 5,
            "userAuthToken": "XXX"
        }
    }

.. csv-table::
    :header: Code ,Description

    1002,Wrong user credentials. 


