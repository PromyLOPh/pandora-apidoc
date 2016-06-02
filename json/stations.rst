.. _stations:

Stations
========

A *station* is a collection of one or more user-supplied *seeds*. Artists or
tracks can be used as seed. Based on the seeds Pandora decides which music to
play.


.. index::
   pair: method; user.getStationList

.. _user-getStationList:

Retrieve station list
---------------------

:Method: user.getStationList

.. csv-table::
    :header: Name ,Type ,Description

    includeStationArtUrl ,boolean ,Includes "artUrl" field in result (optional)
    stationArtSize,string,“W130H130”
    includeAdAttributes,boolean,(optional)
    includeStationSeeds,boolean,(optional)
    includeShuffleInsteadOfQuickMix,boolean,(optional)
    includeRecommendations,boolean,(optional)
    includeExplanations,boolean,(optional)

.. code:: json

    {
       "userAuthToken": "XXX",
       "syncTime": XXX
    }

Currently stationId and stationToken are the same.

QuickMix stations additionally include a list of station ids
(quickMixStationIds) that are currently selected for the mix.

.. csv-table::
    :header: Name ,Type ,Description

    stations.stationId,string,
    stations.stationName,string,
    checksum,string,

.. code:: json

    {
            "stat":"ok",
            "result":{
               "stations":[
                  {
                     "suppressVideoAds":true,
                     "isQuickMix":true,
                     "stationId":"3914377363925265",
                     "stationDetailUrl":"https://www.pandora.com/login?target=%2Fstations%2Fa61985110ea3d6c6c8d8a9c038588b26425ba2910f7abf8b",
                     "isShared":false,
                     "dateCreated":{
                        "date":8,
                        "day":4,
                        "hours":22,
                        "minutes":44,
                        "month":10,
                        "nanos":241000000,
                        "seconds":46,
                        "time":1194590686241,
                        "timezoneOffset":480,
                        "year":107
                     },
                     "stationToken":"3914377363925265",
                     "stationName":"QuickMix",
                     "stationSharingUrl":"https://www.pandora.com/login?target=%2Fshare%2Fstation%2Fa61985110ea3d6c6c8d8a9c038588b26425ba2910f7abf8b",
                     "requiresCleanAds":true,
                     "allowRename":false,
                     "allowAddMusic":false,
                     "quickMixStationIds":[
                        "339646069607180561",
                        "339644480469281041"
                     ],
                     "allowDelete":false
                  }
               ],
               "checksum":"99776ddd31ad798895578593e78e3691"
            }
         }


.. index::
   pair: method; user.getStationListChecksum

.. _user-getStationListChecksum:

Check station list for modifications
------------------------------------

:Method: user.getStationListChecksum

To check if the station list was modified by another client the checksum can be
fetched. No parameters are required for this request.

The response contains the new checksum.

.. csv-table::
    :header: Name,Type,Description

    checksum,string,

.. code:: json

    {
        "stat":"ok",
         "result":{
              "checksum":"99776ddd31ad798895578593e78e3691"
         }
     }

Add new station
---------------

New stations can be created by searching for an artist/song or using a track
from a playlist.


.. index::
   pair: method; music.search

.. _music-search:

Search
^^^^^^

:Method: music.search

This is a free text search that matches artist and track names.

.. csv-table::
    :header: Name ,Type ,Description

    searchText ,string ,Artist name or track title
    includeNearMatches,bool,(optional)
    includeGenreStations,bool,(optional)

.. code:: json

    {
        "searchText": "encore",
        "userAuthToken": "XXX",
        "syncTime": 1335869287
    }

Matching songs, artists, and genre stations are returned in three separate lists.

.. csv-table::
    :header: Name ,Type ,Description

    songs.musicToken ,string , Token starts with 'S' followed by one or more digits (e.g. 'S1234567').
    artists.musicToken ,string , Results can be either for artists (token starts with 'R') or composers (token starts with 'C').
    genreStations.musicToken, string, Token starts with 'G' followed by one or more digits (e.g. 'G123').

.. code:: json

    {
        "stat": "ok",
        "result": {
            "nearMatchesAvailable": true,
            "explanation": "",
            "songs": [{
                "artistName": "Jason DeRulo",
                "musicToken": "S1508963",
                "songName": "Encore",
                "score": 100
            }],
            "artists": [{
                "artistName": "Encore",
                "musicToken": "R175304",
                "likelyMatch": false,
                "score": 100
            }],
            "genreStations": [{
                "musicToken": "G123",
                "score": 100,
                "stationName": u"Today's Encore"}
            }]
        }
    }


.. index::
   pair: method; user.createStation

.. _station-createStation:

Create
^^^^^^

:Method: station.createStation

Stations can either be created with a musicToken obtained by
:ref:`music-search` or trackToken from playlists (:ref:`station-getPlaylist`).
The latter needs a musicType to specify whether the track itself or its artist
should be used as seed.

.. csv-table::
   :header: Name,Type,Description

   trackToken,string,See :ref:`station-getPlaylist`
   musicType,string,“song” or “artist”
   musicToken,string,See :ref:`music-search`


.. index::
   pair: method; station.addMusic

.. _station-addMusic:

Add seed
--------

:Method: station.addMusic

:ref:`music-search` results can be used to add new seeds to an existing
station.

.. csv-table::
   :header: Name,Type,Description

   stationToken,string,"Existing station, see :ref:`user-getStationList`"
   musicToken,string,"See :ref:`music-search`"

.. code:: json

    {
        "musicToken": "R1119",
        "stationToken": "1181753543028256237",
        "userAuthToken": "XXX",
        "syncTime": 1404912202
    }

.. csv-table::
   :header: Name,Type,Description

   seedId,string,Can be used to remove seed with :ref:`station-deleteMusic`

.. code:: json

    {
        "stat": "ok",
        "result": {
            "artistName": "Foo Fighters",
            "musicToken": "3bcf3f314419f974",
            "seedId": "2123197691273031149",
            "artUrl": "http://cont-dc6-1.pandora.com/images/public/amg/portrait/pic200/drP900/P972/P97242B3S6P.jpg",
            "dateCreated": {
                "date": 9,
                "day": 3,
                "hours": 6,
                "minutes": 23,
                "month": 6,
                "seconds": 22,
                "time": 1404912202722,
                "timezoneOffset": 420,
                "year": 114
            }
        }
    }


.. index::
   pair: method; station.deleteMusic

.. _station-deleteMusic:

Remove seed
-----------

:Method: station.deleteMusic

Seeds can be removed from a station, except for the last one.

.. csv-table::
   :header: Name,Type,Description

   seedId,string,See :ref:`station-getStation` and :ref:`station-addMusic`

.. code:: json

    {
        "seedId": "1230715903914683885",
        "userAuthToken": "XXX",
        "syncTime": 1404912023
    }

This method does not return data.

.. csv-table::
   :header: Code,Description

   1032,Last seed cannot be removed


.. index::
   pair: method; station.renameStation

.. _station-renameStation:

Rename station
--------------

:Method: station.renameStation

.. csv-table::
   :header: Name,Type,Description

   stationToken,string,"Existing station, see :ref:`user-getStationList`"
   stationName,string,New station name


.. index::
   pair: method; station.deleteStation

.. _station-deleteStation:

Delete station
--------------

:Method: station.deleteStation

.. csv-table::
   :header: Name,Type,Description

   stationToken,string,"Existing station, see :ref:`user-getStationList`"

.. code:: json

    {
        "stationToken": "374145764047334893",
        "userAuthToken": "XXX",
        "syncTime": 1404911699
    }

No data is returned in response.


.. index::
   pair: method; station.getStation

.. _station-getStation:

Retrieve extended station information
-------------------------------------

:Method: station.getStation

Extended station information includes seeds and feedback.

.. csv-table::
   :header: Name,Type,Description

   stationToken,string,
   includeExtendedAttributes,bool,

.. code:: json

    {
        "stationToken": "374145764047334893",
        "includeExtendedAttributes": true,
        "userAuthToken": "XXX",
        "syncTime": 1404910732
    }

.. csv-table::
   :header: Name,Type,Description

   music,object,"Station seeds, see :ref:`station-addMusic`"
   music.songs,list,Song seeds
   music.artists,list,Artist seeds
   feedback,object,Feedback added by :ref:`station-addFeedback`
   feedback.thumbsUp,list,
   feedback.thumbsDown,list,

.. code:: json

     {
         "stat": "ok",
         "result": {
             "suppressVideoAds": false,
             "stationId": "374145764047334893",
             "allowAddMusic": true,
             "dateCreated": {
                 "date": 15,
                 "day": 6,
                 "hours": 7,
                 "minutes": 34,
                 "month": 0,
                 "nanos": 874000000,
                 "seconds": 21,
                 "time": 1295105661874,
                 "timezoneOffset": 480,
                 "year": 111
             },
             "stationDetailUrl": "https://www.pandora.com/login?target=%2Fstations%2Fc644756145fc3f5df1916901125ee697495159685ae39575",
             "artUrl": "http://cont-1.p-cdn.com/images/public/amz/5/2/8/5/075678235825_500W_498H.jpg",
             "requiresCleanAds": false,
             "stationToken": "374145764047334893",
             "stationName": "Winter Radio",
             "music": {
                 "songs": [{
                     "seedId": "428301990230109677",
                     "artistName": "Tori Amos",
                     "dateCreated": {
                         "date": 15,
                         "day": 6,
                         "hours": 7,
                         "minutes": 34,
                         "month": 0,
                         "nanos": 873000000,
                         "seconds": 21,
                         "time": 1295105661873,
                         "timezoneOffset": 480,
                         "year": 111
                     },
                     "artUrl": "http://cont-sjl-1.pandora.com/images/public/amz/5/2/8/5/075678235825_130W_130H.jpg",
                     "songName": "Winter",
                     "musicToken": "87ef9db1c3f04330"
                 }],
                 "artists": []
             },
             "isShared": false,
             "allowDelete": true,
             "genre": ["Rock"],
             "isQuickMix": false,
             "allowRename": true,
             "stationSharingUrl": "https://www.pandora.com/login?target=%2Fshare%2Fstation%2Fc644756145fc3f5df1916901125ee697495159685ae39575",
             "feedback": {
                 "thumbsUp": [{
                     "dateCreated": {
                         "date": 28,
                         "day": 5,
                         "hours": 13,
                         "minutes": 57,
                         "month": 2,
                         "nanos": 760000000,
                         "seconds": 49,
                         "time": 1396040269760,
                         "timezoneOffset": 420,
                         "year": 114
                     },
                     "albumArtUrl": "http://cont-1.p-cdn.com/images/public/amz/9/7/1/4/900004179_130W_130H.jpg",
                     "musicToken": "d33dd0c199ebaf28425ba2910f7abf8b",
                     "songName": "Hey Lover",
                     "artistName": "Keri Noble",
                     "feedbackId": "-7239441039566426643",
                     "isPositive": true
                 }],
                 "totalThumbsUp": 20,
                 "totalThumbsDown": 5,
                 "thumbsDown": [{
                     "dateCreated": {
                         "date": 28,
                         "day": 5,
                         "hours": 10,
                         "minutes": 43,
                         "month": 2,
                         "nanos": 637000000,
                         "seconds": 30,
                         "time": 1396028610637,
                         "timezoneOffset": 420,
                         "year": 114
                     },
                     "albumArtUrl": "http://cont-ch1-1.pandora.com/images/public/amz/9/0/5/1/724383771509_130W_130H.jpg",
                     "musicToken": "5a0018da7876f6e7",
                     "songName": "Talk Show Host",
                     "artistName": "Radiohead",
                     "feedbackId": "-7241622182873125395",
                     "isPositive": false
                 }]
             }
         }
     }


.. index::
   pair: method; station.deleteFeedback

.. _station-deleteFeedback:

Remove feedback
---------------

:Method: station.deleteFeedback

Feedback added by :ref:`station-addFeedback` can be removed from the station.

.. csv-table::
   :header: Name,Type,Description

   feedbackId,string,See :ref:`station-getStation`

.. code:: json

    {
        "feedbackId": "3738252050522320365",
        "userAuthToken": "XXX",
        "syncTime": 1404910760
    }

This method has does not return data.


.. index::
   pair: method; station.getGenreStations

.. _station-getGenreStations:

Predefined stations
-------------------

:Method: station.getGenreStations

Pandora provides a list of predefined stations (“genre stations”). The request
has no parameters.

Each station belongs to one category, usually a genre name. stationToken can be
used as musicToken to create a new station with :ref:`station-createStation`.

.. csv-table::
    :header: Name ,Type ,Description

    categories ,array ,List of categories
    categories.stations ,array ,List of stations in category
    categories.stations.stationToken,string,"Actually a musicToken, see :ref:`station-createStation`"
    catogories.categoryName,string,Category name

.. code:: json

    {
        "stat": "ok",
        "result": {
            "categories": [{
                "stations": [{
                    "stationToken": "G165",
                    "stationName": "90s Alternative ",
                    "stationId": "G165"
                }],
                "categoryName": "Alternative"
            }]
        }
    }


.. index::
   pair: method; station.getGenreStationsChecksum

.. _station-getGenreStationsChecksum:

Checksum
^^^^^^^^

:Method: station.getGenreStationsChecksum

See :ref:`user-getStationListChecksum`.

.. csv-table::
    :header: Name ,Type ,Description

    includeGenreCategoryAdUrl,bool,(optional)

.. csv-table::
    :header: Name ,Type ,Description

    checksum,string,


.. index::
   pair: method; station.shareStation

.. _station-shareStation:

Share Station
-------------

:Method: station.shareStation

Shares a station with the specified email addresses. that emails is a string array

.. csv-table::
    :header: Name ,Type ,Description
    
    stationId,string,See :ref:`user-getStationList`
    stationToken,string,See :ref:`user-getStationList`
    emails,string[],A list of emails to share the station with   


.. index::
   pair: method; station.transformSharedStation

.. _station-transformSharedStation:

Transform shared station
------------------------

:Method: station.transformSharedStation

Stations created by other users are added as reference to the user’s station
list. These stations cannot be modified (i.e. rate tracks) unless transformed.

.. csv-table::
    :header: Name ,Type ,Description

    stationToken,string,See :ref:`user-getStationList`


.. index::
   pair: method; user.setQuickMix

.. _user-setQuickMix:

Modify QuickMix
---------------

:Method: user.setQuickMix

.. csv-table::
    :header: Name ,Type ,Description

    quickMixStationIds ,array ,List of station id’s (strings)

.. code:: json

    {
        "quickMixStationIds": ["404958383414849005", "403387202773593581"],
        "userAuthToken": "XXX",
        "syncTime": 1338211186
    }

The response contains no data.
