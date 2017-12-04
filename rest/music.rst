.. _rest-music:

=====
Music
=====

.. _rest-v1-music-artist:

Artist
======

:Endpoint: /v1/music/artist

Request
-------
.. code:: json

	{
		"token": "R734008"
	}

Response
--------
.. code:: json

  {
    "listenerCount": 11991,
    "isBookmarked": false,
    "discography": [
      {
        "musicId": "L668139",
        "pandoraId": "AL:668139",
        "seoToken": "steve-aoki-louis-tomlinson/just-hold-on-single/ALXVgJnJXrtl9f6",
        "albumTitle": "Just Hold On (Single)",
        "art": [
          {
            "url": "https://mediaserver-cont-dc6-2-v4v6.pandora.com/images/public/int/6/5/6/3/0617465833656_90W_90H.jpg",
            "size": 90
          },
          {
            "url": "https://mediaserver-cont-sv5-2-v4v6.pandora.com/images/public/int/6/5/6/3/0617465833656_130W_130H.jpg",
            "size": 130
          },
          {
            "url": "https://cont-2.p-cdn.com/images/public/int/6/5/6/3/0617465833656_500W_500H.jpg",
            "size": 500
          },
          {
            "url": "https://cont-1.p-cdn.com/images/public/int/6/5/6/3/0617465833656_640W_640H.jpg",
            "size": 640
          },
          {
            "url": "https://cont-1.p-cdn.com/images/public/int/6/5/6/3/0617465833656_1080W_1080H.jpg",
            "size": 1080
          }
        ],
        "year": "2016"
      }
    ],
    "similar": [
      {
        "musicId": "R355704",
        "pandoraId": "AR:355704",
        "name": "One Direction",
        "art": [
          {
            "url": "https://mediaserver-cont-dc6-1-v4v6.pandora.com/images/public/rovi/portrait/2/9/5/6/MN0002766592_200W.jpg",
            "size": 200
          },
          {
            "url": "https://mediaserver-cont-sv5-3-v4v6.pandora.com/images/public/rovi/portrait/2/9/5/6/MN0002766592_640W.jpg",
            "size": 640
          },
          {
            "url": "https://mediaserver-cont-sv5-1-v4v6.pandora.com/images/public/rovi/portrait/2/9/5/6/MN0002766592.jpg",
            "size": 1080
          }
        ],
        "seoToken": "1-direction/ARtp2br9jh6pVX4",
        "detailUrl": "https://www.pandora.com/artist/1-direction/ARtp2br9jh6pVX4"
      }
    ],
    "events": [],
    "musicId": "R734008",
    "pandoraId": "AR:734008",
    "name": "Steve Aoki & Louis Tomlinson",
    "art": [],
    "seoToken": "steve-aoki-louis-tomlinson/ARkmbKd6rz2Xq79",
    "detailUrl": "https://www.pandora.com/artist/steve-aoki-louis-tomlinson/ARkmbKd6rz2Xq79"
  }