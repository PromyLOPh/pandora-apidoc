.. _rest-stations:

========
Stations
========

.. _rest-v1-station-getStations:

Get Stations
============

:Endpoint: /v1/station/getStations

Request
-------
.. code:: json

	{
		"pageSize": 250
	}

Response
--------
.. code:: json

    {
        "totalStations": 2,
        "sortedBy": "lastPlayedTime",
        "index": 0,
        "stations": [
            {
                "stationId": "12345",
                "stationFactoryPandoraId": "SF:12345:123",
                "pandoraId": "ST:12345",
                "name": "Chill Out Radio",
                "art": [
                    {
                        "url": "https://mediaserver-cont-sv5-2-v4v6.pandora.com/images/public/int/9/2/0/5/634904045029_90W_90H.jpg",
                        "size": 90
                    },
                    {
                        "url": "https://mediaserver-cont-dc6-2-v4v6.pandora.com/images/public/int/9/2/0/5/634904045029_130W_130H.jpg",
                        "size": 130
                    },
                    {
                        "url": "https://mediaserver-cont-sv5-3-v4v6.pandora.com/images/public/int/9/2/0/5/634904045029_500W_500H.jpg",
                        "size": 500
                    },
                    {
                        "url": "https://mediaserver-cont-sv5-3-v4v6.pandora.com/images/public/int/9/2/0/5/634904045029_640W_640H.jpg",
                        "size": 640
                    },
                    {
                        "url": "https://cont-2.p-cdn.com/images/public/int/9/2/0/5/634904045029_1080W_1080H.jpg",
                        "size": 1080
                    }
                ],
                "dateCreated": "2017-10-27T20:10:33.202-07:00",
                "lastPlayed": "2017-10-27T21:36:04.426-07:00",
                "totalPlayTime": 987,
                "isNew": false,
                "allowDelete": true,
                "allowRename": false,
                "allowEditDescription": false,
                "allowAddSeed": false,
                "isShared": false,
                "isTransformAllowed": false,
                "isOnDemandEditorialStation": false,
                "isAdvertiserStation": false,
                "canShuffleStation": true,
                "canAutoshare": true,
                "advertisingKey": "",
                "isArtistMessagesEnabled": true,
                "isThumbprint": false,
                "isShuffle": false,
                "genre": [
                    "Rock",
                    "Dance / Electronica"
                ],
                "genreSponsorship": "G464",
                "adGenre": "electronica",
                "antiTarget": false,
                "initialSeed": {
                    "musicId": "G464",
                    "pandoraId": "GE:464",
                    "genre": {
                        "stationName": "Chill Out",
                        "isRedirect": false,
                        "isComedy": false
                    },
                    "listenerCount": 4165328,
                    "art": [
                        {
                            "url": "https://mediaserver-cont-dc6-1-v4v6.pandora.com/images/public/int/9/2/0/5/634904045029_90W_90H.jpg",
                            "size": 90
                        },
                        {
                            "url": "https://mediaserver-cont-dc6-1-v4v6.pandora.com/images/public/int/9/2/0/5/634904045029_130W_130H.jpg",
                            "size": 130
                        },
                        {
                            "url": "https://mediaserver-cont-dc6-2-v4v6.pandora.com/images/public/int/9/2/0/5/634904045029_500W_500H.jpg",
                            "size": 500
                        },
                        {
                            "url": "https://mediaserver-cont-ch1-2-v4v6.pandora.com/images/public/int/9/2/0/5/634904045029_640W_640H.jpg",
                            "size": 640
                        },
                        {
                            "url": "https://cont-1.p-cdn.com/images/public/int/9/2/0/5/634904045029_1080W_1080H.jpg",
                            "size": 1080
                        }
                    ]
                },
                "adkv": {
                    "artist": "G464",
                    "genre": "electronica",
                    "clean": "0",
                    "gcat": "G464"
                },
                "creatorWebname": "example",
                "artId": "images/public/int/9/2/0/5/634904045029"
            },
            {
                "stationId": "12345",
                "stationFactoryPandoraId": "SF:12345:0",
                "pandoraId": "TT:0",
                "name": "Thumbprint Radio",
                "description": "Music inspired by your 999 thumbs from across all your stations.",
                "art": [
                    {
                        "url": "https://mediaserver-cont-sv5-3-v4v6.pandora.com/images/public/devicead/t/r/a/m/daartpralbumart_90W_90H.jpg",
                        "size": 90
                    },
                    {
                        "url": "https://cont-2.p-cdn.com/images/public/devicead/t/r/a/m/daartpralbumart_130W_130H.jpg",
                        "size": 130
                    },
                    {
                        "url": "https://mediaserver-cont-dc6-1-v4v6.pandora.com/images/public/devicead/t/r/a/m/daartpralbumart_500W_500H.jpg",
                        "size": 500
                    }
                ],
                "dateCreated": "2017-10-27T20:10:33.202-07:00",
                "lastPlayed": "2017-10-27T21:36:04.426-07:00",
                "totalPlayTime": 99999,
                "isNew": false,
                "allowDelete": true,
                "allowRename": false,
                "allowEditDescription": false,
                "allowAddSeed": false,
                "isShared": false,
                "isTransformAllowed": false,
                "isOnDemandEditorialStation": false,
                "isAdvertiserStation": false,
                "canShuffleStation": false,
                "canAutoshare": true,
                "advertisingKey": "",
                "isArtistMessagesEnabled": false,
                "isThumbprint": true,
                "thumbprintThumbCount": 999,
                "thumbprintProcessSkips": true,
                "thumbprintShareArt": "https://mediaserver-cont-sv5-1-v4v6.pandora.com/images/public/devicead/t/r/a/m/daartprfbalbumart_1200W_630H.jpg",
                "shareName": "example's Thumbprint Radio",
                "isShuffle": false,
                "genre": [],
                "adkv": {
                    "artist": "",
                    "genre": "thumbprintradio",
                    "clean": "0",
                    "gcat": "thumbprintradio"
                },
                "creatorWebname": "example",
                "artId": "images/public/devicead/t/r/a/m/daartpralbumart",
                "dominantColor": "0c81c6"
            }
        ]
    }
