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
        "totalStations": 1,
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
            }
        ]
    }

.. _rest-v1-station-trackStarted:

Track Started
=============

:Endpoint: /v1/station/trackStarted

Request
-------
.. code:: json

	{
		"trackToken": "PGFM66cl6W77Vs1yFGsa4D5KjNhU3GlaT1Oa1wNdpYk2_Q0RDUKG3_c0_PX7KYP55a8Lf2OA5ToT025KvGWH-Eg"
	}

Response
--------
.. code:: json

	{
	  "updateFacebookInfo": false
	}

.. _rest-v1-station-playbackPaused:

Playback Paused
===============

:Endpoint: /v1/station/playbackPaused

Request
-------
.. code:: json

	{
		"sync": false
	}

Response
--------
.. code:: json

	{}

.. _rest-v1-station-createStation:

Create Station
==============

:Endpoint: /v1/station/createStation

Request
-------
.. code:: json

	{
		"stationCode": "mcR750856",
		"stationName": "",
		"searchQuery": "test",
		"pandoraId": null,
		"creativeId": null,
		"lineId": null,
		"createionSource": null,
	}

Response
--------
.. code:: json

	{
	  "stationId": "3815417889522984361",
	  "stationFactoryPandoraId": "SF:16722:750856",
	  "pandoraId": "ST:0:3815417889522984361",
	  "name": "Tee Grizzley Radio",
	  "art": [
	    {
	      "url": "https://mediaserver-cont-sv5-1-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_90W_90H.jpg",
	      "size": 90
	    },
	    {
	      "url": "https://mediaserver-cont-ch1-1-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_130W_130H.jpg",
	      "size": 130
	    },
	    {
	      "url": "https://mediaserver-cont-sv5-1-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_500W_500H.jpg",
	      "size": 500
	    },
	    {
	      "url": "https://mediaserver-cont-dc6-2-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_640W_640H.jpg",
	      "size": 640
	    },
	    {
	      "url": "https://mediaserver-cont-sv5-3-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_1080W_1080H.jpg",
	      "size": 1080
	    }
	  ],
	  "dateCreated": "2017-12-04T16:26:05.041-08:00",
	  "isNew": true,
	  "allowDelete": true,
	  "allowRename": true,
	  "allowEditDescription": true,
	  "allowAddSeed": true,
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
	    "Rap / Hip-Hop"
	  ],
	  "genreSponsorship": "R750856",
	  "adGenre": "electronica",
	  "antiTarget": false,
	  "initialSeed": {
	    "musicId": "R750856",
	    "pandoraId": "AR:750856",
	    "artist": {
	      "artistName": "Tee Grizzley",
	      "isComposer": false,
	      "isComedy": false,
	      "artistDetailUrl": "https://www.pandora.com/artist/tee-grizzley/ARpZvrqrjftKpcm"
	    },
	    "listenerCount": 899699,
	    "seoToken": "tee-grizzley/ARpZvrqrjftKpcm",
	    "art": [
	      {
	        "url": "https://mediaserver-cont-ch1-2-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_90W_90H.jpg",
	        "size": 90
	      },
	      {
	        "url": "https://mediaserver-cont-sv5-1-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_130W_130H.jpg",
	        "size": 130
	      },
	      {
	        "url": "https://cont-2.p-cdn.com/images/public/int/4/4/6/4/814908024644_500W_500H.jpg",
	        "size": 500
	      },
	      {
	        "url": "https://mediaserver-cont-dc6-1-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_640W_640H.jpg",
	        "size": 640
	      },
	      {
	        "url": "https://cont-2.p-cdn.com/images/public/int/4/4/6/4/814908024644_1080W_1080H.jpg",
	        "size": 1080
	      }
	    ]
	  },
	  "adkv": {
	    "artist": "R750856",
	    "genre": "electronica",
	    "clean": "0",
	    "gcat": "R750856"
	  },
	  "creatorWebname": "your-username",
	  "artId": "images/public/int/4/4/6/4/814908024644",
	  "dominantColor": "b12121"
	}

.. _rest-v1-station-shuffle:

Shuffle
=======

:Endpoint: /v1/station/shuffle

Request
-------
.. code:: json

	{}

Response
--------
.. code:: json
	
	{
	  "stationId": "94498720962323881",
	  "stationFactoryPandoraId": "SF:21332:0:94498720962323881",
	  "pandoraId": "ST:0:94498720962323881",
	  "name": "Shuffle",
	  "art": [
	    {
	      "url": "https://www.pandora.com/img/shuffle_art_90W_90H.png",
	      "size": 90
	    },
	    {
	      "url": "https://www.pandora.com/img/shuffle_art_130W_130H.png",
	      "size": 130
	    },
	    {
	      "url": "https://www.pandora.com/img/shuffle_art_500W_500H.png",
	      "size": 500
	    },
	    {
	      "url": "https://www.pandora.com/img/shuffle_art_600W_600H.png",
	      "size": 600
	    },
	    {
	      "url": "https://www.pandora.com/img/shuffle_art_640W_640H.png",
	      "size": 640
	    },
	    {
	      "url": "https://www.pandora.com/img/shuffle_art_1080W_1080H.png",
	      "size": 1080
	    }
	  ],
	  "dateCreated": "2009-04-29T18:11:53.151-07:00",
	  "isNew": false,
	  "allowDelete": false,
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
	  "isArtistMessagesEnabled": true,
	  "isThumbprint": false,
	  "isShuffle": true,
	  "shuffleStationIds": [
	    "266232033420667434533",
	    "2378131011990553468169",
	    "21436172367947969449",
	    "3568413019964799131"
	  ],
	  "genre": [],
	  "adkv": {
	    "artist": "R10681",
	    "genre": "none",
	    "clean": "0",
	    "gcat": "none"
	  },
	  "creatorWebname": "your-username",
	  "dominantColor": "c34b75"
	}

.. _rest-v1-station-getStationDetails:

Get Station Details
===================

:Endpoint: /v1/station/getStationDetails

Request
-------
.. code:: json

	{
		"stationId": "3815417889522984361",
		"isCurrentStation": true
	}

Response
--------
.. code:: json

	{
	  "seeds": [
	    {
	      "musicId": "R750856",
	      "pandoraId": "AR:750856",
	      "artist": {
	        "artistName": "Tee Grizzley",
	        "isComposer": false,
	        "isComedy": false,
	        "artistDetailUrl": "https://www.pandora.com/artist/tee-grizzley/ARpZvrqrjftKpcm"
	      },
	      "listenerCount": 899699,
	      "seoToken": "tee-grizzley/ARpZvrqrjftKpcm",
	      "art": [
	        {
	          "url": "https://mediaserver-cont-ch1-1-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_90W_90H.jpg",
	          "size": 90
	        },
	        {
	          "url": "https://mediaserver-cont-dc6-2-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_130W_130H.jpg",
	          "size": 130
	        },
	        {
	          "url": "https://mediaserver-cont-sv5-2-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_500W_500H.jpg",
	          "size": 500
	        },
	        {
	          "url": "https://mediaserver-cont-dc6-2-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_640W_640H.jpg",
	          "size": 640
	        },
	        {
	          "url": "https://cont-2.p-cdn.com/images/public/int/4/4/6/4/814908024644_1080W_1080H.jpg",
	          "size": 1080
	        }
	      ]
	    }
	  ],
	  "positiveFeedbackCount": 0,
	  "negativeFeedbackCount": 0,
	  "stationId": "3815417889522984361",
	  "stationFactoryPandoraId": "SF:16722:750856",
	  "pandoraId": "ST:0:3815417889522984361",
	  "name": "Tee Grizzley Radio",
	  "art": [
	    {
	      "url": "https://mediaserver-cont-sv5-1-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_90W_90H.jpg",
	      "size": 90
	    },
	    {
	      "url": "https://cont-1.p-cdn.com/images/public/int/4/4/6/4/814908024644_130W_130H.jpg",
	      "size": 130
	    },
	    {
	      "url": "https://mediaserver-cont-dc6-1-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_500W_500H.jpg",
	      "size": 500
	    },
	    {
	      "url": "https://mediaserver-cont-ch1-1-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_640W_640H.jpg",
	      "size": 640
	    },
	    {
	      "url": "https://cont-2.p-cdn.com/images/public/int/4/4/6/4/814908024644_1080W_1080H.jpg",
	      "size": 1080
	    }
	  ],
	  "dateCreated": "2017-12-04T16:26:05.041-08:00",
	  "lastPlayed": "2017-12-04T16:26:05.519-08:00",
	  "isNew": false,
	  "allowDelete": true,
	  "allowRename": true,
	  "allowEditDescription": true,
	  "allowAddSeed": true,
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
	    "Rap / Hip-Hop"
	  ],
	  "genreSponsorship": "R750856",
	  "adGenre": "electronica",
	  "antiTarget": false,
	  "initialSeed": {
	    "musicId": "R750856",
	    "pandoraId": "AR:750856",
	    "artist": {
	      "artistName": "Tee Grizzley",
	      "isComposer": false,
	      "isComedy": false,
	      "artistDetailUrl": "https://www.pandora.com/artist/tee-grizzley/ARpZvrqrjftKpcm"
	    },
	    "listenerCount": 899699,
	    "seoToken": "tee-grizzley/ARpZvrqrjftKpcm",
	    "art": [
	      {
	        "url": "https://mediaserver-cont-ch1-2-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_90W_90H.jpg",
	        "size": 90
	      },
	      {
	        "url": "https://mediaserver-cont-dc6-1-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_130W_130H.jpg",
	        "size": 130
	      },
	      {
	        "url": "https://mediaserver-cont-sv5-3-v4v6.pandora.com/images/public/int/4/4/6/4/814908024644_500W_500H.jpg",
	        "size": 500
	      },
	      {
	        "url": "https://cont-2.p-cdn.com/images/public/int/4/4/6/4/814908024644_640W_640H.jpg",
	        "size": 640
	      },
	      {
	        "url": "https://cont-2.p-cdn.com/images/public/int/4/4/6/4/814908024644_1080W_1080H.jpg",
	        "size": 1080
	      }
	    ]
	  },
	  "adkv": {
	    "artist": "R750856",
	    "genre": "electronica",
	    "clean": "0",
	    "gcat": "R750856"
	  },
	  "creatorWebname": "your-username",
	  "artId": "images/public/int/4/4/6/4/814908024644",
	  "dominantColor": "b12121"
	}

.. _rest-v1-station-addFeedback:

Add Feedback
============

:Endpoint: /v1/station/addFeedback

Request
-------
.. code:: json

	{
		"trackToken": "PWqWRL10lu3_Vs1yFGsa4D5UPmVsZ9z-F1Oa1wNdpYk2_Q0RDUKG3_U3vDcuVW3DP4NKGhYA6ecO_SMZISxwpog",
		"isPositive": false
	}

Response
--------
.. code:: json

	{
	  "feedbackId": "6192453069559637",
	  "isPositive": false,
	  "stationId": "3793312577613735337",
	  "stationName": "Pop 2017 Radio",
	  "musicId": "S5582987",
	  "pandoraId": "TR:5582987",
	  "songTitle": "All Time Low",
	  "albumTitle": "The Human Condition (Explicit)",
	  "artistName": "Jon Bellion",
	  "artistSeoToken": "jon-bellion/ARZvh6pgth6qc64",
	  "artistDetailUrl": "https://www.pandora.com/artist/jon-bellion/ARZvh6pgth6qc64",
	  "trackSeoToken": "jon-bellion/human-condition-explicit/all-time-low/TRm7mZKXfxpwK76",
	  "trackDetailUrl": "https://www.pandora.com/artist/jon-bellion/human-condition-explicit/all-time-low/TRm7mZKXfxpwK76",
	  "albumSeoToken": "jon-bellion/human-condition-explicit/ALZrKqJ9dKkvkmX",
	  "sampleUrl": "https://audio-ssl.itunes.apple.com/apple-assets-us-std-000001/AudioPreview18/v4/83/f6/89/83f68945-835b-be1f-5b02-ef153669ef84/mzaf_7005711340359546106.plus.aac.p.m4a",
	  "amazonUrl": "https://www.amazon.com/gp/search/?index=music&field-artist=Jon+Bellion&field-title=The+Human+Condition+%28Explicit%29&tag=wwwpandoracom-20",
	  "amazonDigitalAsin": "B01F9W9CZC",
	  "albumAmazonDigitalAsin": "B01F9W9A5O",
	  "itunesUrl": "http://itunes.apple.com/album/all-time-low/id1111414736?i=1111414908&uo=5&at=11l3Hh&app=itunes",
	  "trackNum": 3,
	  "discNum": 1,
	  "trackLength": 217,
	  "albumArt": [
	    {
	      "url": "https://mediaserver-cont-sv5-3-v4v6.pandora.com/images/public/int/4/5/0/8/00602547858054_90W_90H.jpg",
	      "size": 90
	    },
	    {
	      "url": "https://mediaserver-cont-ch1-1-v4v6.pandora.com/images/public/int/4/5/0/8/00602547858054_130W_130H.jpg",
	      "size": 130
	    },
	    {
	      "url": "https://mediaserver-cont-dc6-2-v4v6.pandora.com/images/public/int/4/5/0/8/00602547858054_500W_500H.jpg",
	      "size": 500
	    },
	    {
	      "url": "https://cont-1.p-cdn.com/images/public/int/4/5/0/8/00602547858054_640W_640H.jpg",
	      "size": 640
	    },
	    {
	      "url": "https://cont-1.p-cdn.com/images/public/int/4/5/0/8/00602547858054_1080W_1080H.jpg",
	      "size": 1080
	    }
	  ]
	}

.. _rest-v1-station-getStationFeedback:

Get Station Feedback
====================

:Endpoint: /v1/station/getStationFeedback

Request
-------
.. code:: json

	{
		"pageSize": 1,
		"startIndex": 0,
		"stationId": "3793312577613735337",
		"positive": false
	}

Response
--------
.. code:: json

	{
	  "total": 1,
	  "feedback": [
	    {
	      "feedbackId": "6192453069559637",
	      "isPositive": false,
	      "stationId": "3793312577613735337",
	      "stationName": "Pop 2017 Radio",
	      "musicId": "S5582987",
	      "pandoraId": "TR:5582987",
	      "songTitle": "All Time Low",
	      "albumTitle": "The Human Condition (Explicit)",
	      "artistName": "Jon Bellion",
	      "artistSeoToken": "jon-bellion/ARZvh6pgth6qc64",
	      "artistDetailUrl": "https://www.pandora.com/artist/jon-bellion/ARZvh6pgth6qc64",
	      "trackSeoToken": "jon-bellion/human-condition-explicit/all-time-low/TRm7mZKXfxpwK76",
	      "trackDetailUrl": "https://www.pandora.com/artist/jon-bellion/human-condition-explicit/all-time-low/TRm7mZKXfxpwK76",
	      "albumSeoToken": "jon-bellion/human-condition-explicit/ALZrKqJ9dKkvkmX",
	      "sampleUrl": "https://audio-ssl.itunes.apple.com/apple-assets-us-std-000001/AudioPreview18/v4/83/f6/89/83f68945-835b-be1f-5b02-ef153669ef84/mzaf_7005711340359546106.plus.aac.p.m4a",
	      "amazonUrl": "https://www.amazon.com/gp/search/?index=music&field-artist=Jon+Bellion&field-title=The+Human+Condition+%28Explicit%29&tag=wwwpandoracom-20",
	      "amazonDigitalAsin": "B01F9W9CZC",
	      "albumAmazonDigitalAsin": "B01F9W9A5O",
	      "itunesUrl": "http://itunes.apple.com/album/all-time-low/id1111414736?i=1111414908&uo=5&at=11l3Hh&app=itunes",
	      "trackNum": 3,
	      "discNum": 1,
	      "trackLength": 217,
	      "albumArt": [
	        {
	          "url": "https://mediaserver-cont-sv5-1-v4v6.pandora.com/images/public/int/4/5/0/8/00602547858054_90W_90H.jpg",
	          "size": 90
	        },
	        {
	          "url": "https://mediaserver-cont-ch1-2-v4v6.pandora.com/images/public/int/4/5/0/8/00602547858054_130W_130H.jpg",
	          "size": 130
	        },
	        {
	          "url": "https://cont-2.p-cdn.com/images/public/int/4/5/0/8/00602547858054_500W_500H.jpg",
	          "size": 500
	        },
	        {
	          "url": "https://mediaserver-cont-sv5-1-v4v6.pandora.com/images/public/int/4/5/0/8/00602547858054_640W_640H.jpg",
	          "size": 640
	        },
	        {
	          "url": "https://mediaserver-cont-ch1-1-v4v6.pandora.com/images/public/int/4/5/0/8/00602547858054_1080W_1080H.jpg",
	          "size": 1080
	        }
	      ]
	    }
	  ]
	}