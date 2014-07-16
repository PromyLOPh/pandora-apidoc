Bookmarks
=========

Users can bookmark artists or songs.


.. index::
   single: user.getBookmarks

.. _user-getBookmarks:

Retrieve bookmarks
------------------

:Method: user.getBookmarks

The request has no parameters.

.. code:: json

    {
        "stat":"ok",
        "result": {
            "artists": [
                {
                    "musicToken": "R130360",
                    "artistName": "Cannabich, Christian",
                    "artUrl": "http://cont-sv5-2.pandora.com/images/public/amz/5/2/9/7/095115137925_500W_488H.jpg",
                    "bookmarkToken": "80982345262345234",
                    "dateCreated": {
                        "nanos": 300000000,
                        "seconds": 22,
                        "year": 112,
                        "month": 4,
                        "hours": 11,
                        "time": 1350566223422,
                        "date": 23,
                        "minutes": 01,
                        "day": 2,
                        "timezoneOffset": 720
                    }
                }
            ],
            "songs": [
                {
                    "sampleUrl": "http://www.pandora.com/favorites/getSample.jsp?token=32458973245b90287345d0234fc34f8b&allowExplicit=true",
                    "sampleGain": "-7.87",
                    "albumName": "Symphony In G Major",
                    "artistName": "Cannabich, Christian",
                    "musicToken": "S2894329",
                    "dateCreated": {
                        "nanos": 300000000,
                        "seconds": 22,
                        "year": 112,
                        "month": 4,
                        "hours": 11,
                        "time": 1350566223422,
                        "date": 23,
                        "minutes": 01,
                        "day": 2,
                        "timezoneOffset": 720
                    },
                    "artUrl": "http://cont-sv5-2.pandora.com/images/public/amz/5/2/9/7/095115137925_500W_488H.jpg",
                    "bookmarkToken": "290832123432459854",
                    "songName": "London Mozart Players, Christian Cannabich: Symphonies"
                }
            ]
        }
     
     }


.. index::
   single: bookmark.addArtistBookmark

.. _bookmark-addArtistBookmark:

Add artist bookmark
-------------------

:Method: bookmark.addArtistBookmark

.. csv-table::
    :header: Name ,Type ,Description

    trackToken,string,

.. code:: json

    {
        "trackToken": "f17ff6c86c11743fc890808e1a1dd6ff5b1dca1a2e260f7d998ba6e7786dd9941c5dd4b345a1008e86862353da1e6cdc78172b4199240c76",
        "userAuthToken": "XXX",
        "syncTime": 1338210690
    }

.. code:: json

    {
        "stat": "ok",
        "result": {
            "artistName": "Wallis Bird",
            "dateCreated": {
                "date": 2,
                "day": 3,
                "hours": 7,
                "minutes": 6,
                "month": 6,
                "seconds": 13,
                "time": 1404309973468,
                "timezoneOffset": 420,
                "year": 114
            },
            "bookmarkToken": "49854851068341741",
            "artUrl": "http://cont-dc6-2.pandora.com/images/public/amg/portrait/pic200/drP900/P998/P99805K1QKS.jpg",
            "musicToken": "R278544"
        }
    }


.. index::
   single: bookmark.addSongBookmark

.. _bookmark-addSongBookmark:

Add song bookmark
-----------------

:Method: bookmark.addSongBookmark

.. csv-table::
    :header: Name ,Type ,Description

    trackToken ,string ,

.. code:: json

    {
        "trackToken": "f17ff6c86c11743fc890808e1a1dd6ff5b1dca1a2e260f7d998ba6e7786dd9941c5dd4b345a1008e86862353da1e6cdc78172b4199240c76",
        "userAuthToken": "XXX",
        "syncTime": 1338210690
    }

.. code:: json

    {
        "stat": "ok",
        "result": {
            "sampleGain": "1.96",
            "musicToken": "S1143982",
            "bookmarkToken": "200207779061968365",
            "sampleUrl": "http://www.pandora.com/favorites/getSample.jsp?token=a74b4f7551e3e174425ba2910f7abf8b&allowExplicit=true",
            "albumName": "The 5th Exotic",
            "songName": "The 5th Exotic",
            "artUrl": "http://cont-sjl-1.pandora.com/images/public/amz/9/4/5/2/800002549_500W_500H.jpg",
            "dateCreated": {
                "date": 28,
                "day": 1,
                "hours": 6,
                "minutes": 11,
                "month": 4,
                "seconds": 31,
                "time": 1338210691404,
                "timezoneOffset": 420,
                "year": 112
            },
            "artistName": "Quantic"
        }
    }

