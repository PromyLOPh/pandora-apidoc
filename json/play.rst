.. _play:

Play
====

.. _station-getPlaylist:

Retrieve playlist
-----------------

:Method: station.getPlaylist

This method *must* be sent over a TLS-encrypted connection.

.. csv-table::
    :header: Name ,Type ,Description

    stationToken ,string ,station token from :ref:`user-getStationList`
    additionalAudioUrl,string,Comma separated list of additional audio formats to return. (optional)
    stationIsStarting,boolean,(optional)
    includeTrackLength,boolean,(optional)
    includeAudioToken,boolean,(optional)
    xplatformAdCapable,boolean,(optional)
    includeAudioReceiptUrl,boolean,(optional)
    includeBackstageAdUrl,boolean,(optional)
    includeSharingAdUrl,boolean,(optional)
    includeSocialAdUrl,boolean,(optional)
    includeCompetitiveSepIndicator,boolean,(optional)
    includeCompletePlaylist,boolean,(optional)
    includeTrackOptions,boolean,(optional)
    audioAdPodCapable,boolean,(optional)

Valid values for additionalAudioUrl are:

- HTTP_40_AAC_MONO
- HTTP_64_AAC
- HTTP_32_AACPLUS
- HTTP_64_AACPLUS
- HTTP_24_AACPLUS_ADTS
- HTTP_32_AACPLUS_ADTS
- HTTP_64_AACPLUS_ADTS
- HTTP_128_MP3
- HTTP_32_WMA 

Usually a playlist contains four tracks.

.. code:: json

    {
         "userAuthToken": "XXX",
         "additionalAudioUrl":  "HTTP_32_AACPLUS_ADTS,HTTP_64_AACPLUS_ADTS",
         "syncTime": 1335841463,
         "stationToken": "121193154444133035"
    }

.. csv-table::
    :header: Name ,Type ,Description

    items.additionalAudioUrl ,array/string ,List of additional audio urls in the requested order or single string if only one format was requested
    items.songRating ,int , "1 if song was given a thumbs up, 0 if song was not rated yet"
    items.audioUrlMap ,object ,Song audio format and bitrates returned differ based on what partner credentials are used.

.. code:: json

    {
         "stat": "ok",
         "result": {
             "items": [{
                 "trackToken": "40b892bc5376e695c2e5c2b347227b85af2761b6aa417f736d9a79319b8f4cb97c9695a5f9a9a32aa2abaed43571235c",
                 "artistName": "Cannabich, Christian",
                 "albumName": "London Mozart Players, Christian Cannabich: Symphonies",
                 "amazonAlbumUrl": "http://www.amazon.com/dp/B000GW8ATU/?tag=wwwpandoracom-20",
                 "songExplorerUrl": "http://www.pandora.com/xml/music/song/london-mozart-players/christian-cannabich-symphonies/2-andantino?explicit=false",
                 "albumArtUrl": "http://cont-sv5-2.pandora.com/images/public/amz/5/2/9/7/095115137925_500W_488H.jpg",
                 "artistDetailUrl": "http://www.pandora.com/christian-cannabich?...",
                 "audioUrlMap": {
                     "highQuality": {
                         "bitrate": "64",
                         "encoding": "aacplus",
                         "audioUrl": "http://audio-sjl-t1-2.pandora.com/access/166132182435087962.mp4?...",
                         "protocol": "http"
                     },
                     "mediumQuality": {
                         "bitrate": "64",
                         "encoding": "aacplus",
                         "audioUrl": "http://t1-2.cdn.pandora.com/access/4127124196771074419.mp4?...",
                         "protocol": "http"
                     },
                     "lowQuality": {
                         "bitrate": "32",
                         "encoding": "aacplus",
                         "audioUrl": "http://audio-sv5-t1-1.pandora.com/access/3464788359714661029.mp4?...",
                         "protocol": "http"
                     }
                 },
                 "itunesSongUrl": "http://click.linksynergy.com/fs-bin/stat?...",
                 "additionalAudioUrl": [
                     "http://t1-2.cdn.pandora.com/access/6705986462049243054.mp4?...",
                     "http://audio-sjl-t1-1.pandora.com/access/2473529637452270302.mp4?..."
                 ],
                 "amazonAlbumAsin": "B000GW8ATU",
                 "amazonAlbumDigitalAsin": "B003H37NN4",
                 "artistExplorerUrl": "http://www.pandora.com/xml/music/composer/christian-cannabich?explicit=false",
                 "songName": "Symphony In G Major",
                 "albumDetailUrl": "http://www.pandora.com/london-mozart-players/christian-cannabich-symphonies?...",
                 "songDetailUrl": "http://www.pandora.com/london-mozart-players/christian-cannabich-symphonies/2-andantino?...",
                 "stationId": "121193154444133035",
                 "songRating": 0,
                 "trackGain": "10.09",
                 "albumExplorerUrl": "http://www.pandora.com/xml/music/album/london-mozart-players/christian-cannabich-symphonies?explicit=false",
                 "allowFeedback": true,
                 "amazonSongDigitalAsin": "B003H39AGW",
                 "nowPlayingStationAdUrl": "http://ad.doubleclick.net/pfadx/pand.android/prod.nowplaying..."
             }, {
                 "adToken": "121193154444133035-none"
             }, 
             ]
         }
    }

.. _station-addFeedback:

Rate track
----------

:Method: station.addFeedback

Songs can be “loved” or “banned”. Both influence the music played on the
station. Banned songs are never played again on this particular station.

.. csv-table::
    :header: Name,Type,Description

    stationToken,string,
    trackToken,string,
    isPositive,boolean,``false`` bans track

.. code:: json

    {
        "stationToken": "374145764047334893",
        "trackToken": "fcc2298ec4b1c93e73ad4b2813ceca0dba565bbbe03d8a78bad65ee89a7aaf4d0b3b11954fe6ab08794283f8ef1d44bfc32ce9f8e0513bec",
        "isPositive": false,
        "userAuthToken": "XXX",
        "syncTime": 1404911036
    }

.. csv-table::
   :header: Name,Type,Description

    dateCreated,object,
    musicToken,string,
    songName,string,
    totalThumbsUp,int,
    feedbackId,string,See :ref:`station-deleteFeedback`
    isPositive,boolean,

.. code:: json

    {
        "stat": "ok",
        "result": {
            "totalThumbsDown": 4,
            "stationPersonalizationPercent": 57,
            "dateCreated": {
                "date": 9,
                "day": 3,
                "hours": 6,
                "minutes": 3,
                "month": 6,
                "seconds": 56,
                "time": 1404911036840,
                "timezoneOffset": 420,
                "year": 114
            },
            "albumArtUrl": "http://cont-sv5-2.pandora.com/images/public/amz/2/2/9/5/094632175922_130W_130H.jpg",
            "musicToken": "23234b0abdbeb37d",
            "songName": "Nothing Compares 2 U",
            "artistName": "Sinead O'Connor",
            "totalThumbsUp": 20,
            "feedbackId": "21955050420286614",
            "isPositive": false
        }
    }


.. _user-sleepSong:

Temporarily ban track
---------------------

:Method: user.sleepSong

A song can be banned *from all stations* temporarily (one month).

.. csv-table::
    :header: Name ,Type ,Description

    trackToken ,string ,See :ref:`station-getPlaylist`

.. code:: json

    {
        "trackToken": "d6aa37c60833f12150c4e2ba172c46f24590ebc49df948b6fb7117314c41c8e7d4faee3568884468d9509db2ab998dafdbc4093baf8c38ef",
        "userAuthToken": "XXX",
        "syncTime": 1336386838
    }

Nothing is returned in the response.

.. _track-explainTrack:

Explain track choice
--------------------

:Method: track.explainTrack

Get (incomplete) list of attributes assigned to song by Music Genome Project.

.. csv-table::
    :header: Name ,Type ,Description

    trackToken ,string ,See :ref:`station-getPlaylist`

.. code:: json

    {
        "trackToken": "94f36e09e341780c2ee7ebbb3581a55c4f2066dbaa60f2ee253ede5bc407fbd3c4f6db7ed00f92312437e020e0bf0e05d2924742c2ccece2",
        "userAuthToken": "XXX",
        "syncTime": 1336675993
    }

The request returns a list of attributes. Note that the last item is not an
actual attribute.

.. csv-table::
    :header: Name ,Type ,Description

    explanations ,array ,

.. code:: json

    {
        "stat": "ok",
        "result": {
            "explanations": [{
                "focusTraitName": "trance roots",
                "focusTraitId": "F7524"
            },
            {
                "focusTraitName": "many other similarities identified in the Music Genome Project",
                "focusTraitId": "F4797"
            }]
        }
    }


