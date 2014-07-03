.. _stations:

Stations
========

A *station* is a collection of one or more user-supplied *seeds*. Artists or
tracks can be used as seed. Based on the seeds Pandora decides which music to
play.

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

.. _music-search:

Search
^^^^^^

:Method: music.search

This is a free text search that matches artist and track names.

.. csv-table::
    :header: Name ,Type ,Description

    searchText ,string ,Artist name or track title

.. code:: json

    {
        "searchText": "encore",
        "userAuthToken": "XXX",
        "syncTime": 1335869287
    }

Matching songs and artists are returned in two separate list.

.. csv-table::
    :header: Name ,Type ,Description

    songs.musicToken and artists.musicToken ,string ,

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
            }]
        }
    }

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

.. _station-renameStation:

Rename station
--------------

:Method: station.renameStation

.. csv-table::
   :header: Name,Type,Description

   stationToken,string,"Existing station, see :ref:`user-getStationList`"
   stationName,string,New station name

.. _station-deleteStation:

Delete station
--------------

:Method: station.deleteStation

.. csv-table::
   :header: Name,Type,Description

   stationToken,string,"Existing station, see :ref:`user-getStationList`"

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

