.. _ads:

Advertisements
==============

Pandora is ad-free for Pandora One users. For all other account types, the playlist returned by
:ref:`station-getPlaylist` or :ref:`auth-userLogin` will contain tracks with adToken values
for the advertisements that should be played (if audioUrl is provided) or displayed using imageUrl and bannerAdMap.


.. index::
   pair: method; ad.getAdMetadata

.. _ad-getAdMetadata:

Retrieve ad metadata
--------------------

:Method: ad.getAdMetadata

Retrieve the metadata for the associated advertisement token (usually provided by one of the other methods responsible for retrieving the playlist).

.. csv-table::
    :header: Name, Type, Description

    adToken, string, The adToken to retrieve the metadata for. (see :ref:`station-getPlaylist`)
    returnAdTrackingTokens, boolean, (optional - but the adTrackingTokens are required by :ref:`ad-registerAd` )
    supportAudioAds, boolean, audioUrl links for the ads are included in the results if set to 'True'. (optional)
    includeBannerAd, boolean, bannerAdMap containing an HTML fragment that can be embedded in web pages is included in the results if set to 'True'. (optional)

.. code:: json

    {
        "stat": "ok",
        "result": {
            "clickThroughUrl": "http://adclick.g.doubleclick.net/aclk?sa=L&ai=BN-k_Zu53Vsr-F8-MlALj2rngAdjY8PcIAAAAEAEgADgAWPiivbTzAmDJBoIBF2NhLXB1Yi0yMTY0NjIyMzg3Njg3ODgysgEYd3d3LmRjbGstZGVmYXVsdC1yZWYuY29tugEJZ2ZwX2ltYWdlyAEJ2gEgaHR0cDovL3d3dy5kY2xrLWRlZmF1bHQtcmVmLmNvbS-YApNYwAIC4AIA6gIhNDIwNC9wYW5kLmFuZHJvaWQvcHJvZC5ub3dwbGF5aW5n-AKB0h6QA6QDmAOkA6gDAeAEAaAGINgHAA&num=0&sig=AOD64_1dqywjcCPaB_sDzcmIjy7yPRJRbQ&client=ca-pub-2164622387687882&adurl=https://www.att.com/shop/wireless/devices/prepaidphones.html",
            "imageUrl": "http://cont-1.p-cdn.com/images/public/devicead/g/e/3/f/daarv2828725klf3eg_500W_500H.jpg",
            "audioUrlMap": {
                "highQuality": {
                    "bitrate": "64",
                    "encoding": "aacplus",
                    "audioUrl": "http://audio-ch1-t2-1-v4v6.pandora.com/access/4070162610719767146.mp4?version=4&lid=1797938999&token=CQ7xvDEck%2FutSGT4CwBfabSJD9DGqEv%2Bl5etfRYIcRtr6aQHd4ske3UE2%2FqzigYDNXjm6Mnh8CECeE%2F%2BQOGhTLY2zKBF260WCb7gTEgdPyFZOLSWfwV6Pi%2FPkF0BtBFGaCmIRLeo0H%2Fu3gyLDuySYPeIBO36SCttM%2B%2BriDe0IDv8EqoAj6BbM3frQiXF3vh%2BNCQoHBBrhLLaqocNu1pAOajQgyMGHMBy%2BKW8%2BhdRPr656jh81KwV%2FcUz%2BX%2Bri0udeRI8iSWR1bewgJdGtMQe3pzSZ1w3V16DAk%2Bi2hTOJXGCdNOLPQjC1GUBKVhdRJTU0uXk9dE8a%2Bn%2Bp2kuMcnRqaXro9Ya%2Ff4U0676v0JwseMng%2FGQp9ehJlbPzwtx5n0H",
                    "protocol": "http"
                },
                "mediumQuality": {
                    "bitrate": "64",
                    "encoding": "aacplus",
                    "audioUrl": "http://audio-ch1-t2-2-v4v6.pandora.com/access/2108163933346668833.mp4?version=4&lid=1797938999&token=CQ7xvDEck%2FutSGT4CwBfabSJD9DGqEv%2Bl5etfRYIcRtr6aQHd4ske3UE2%2FqzigYDNXjm6Mnh8CECeE%2F%2BQOGhTLY2zKBF260WCb7gTEgdPyFZOLSWfwV6Pi%2FPkF0BtBFGaCmIRLeo0H%2Fu3gyLDuySYPeIBO36SCttM%2B%2BriDe0IDv8EqoAj6BbM3frQiXF3vh%2BNCQoHBBrhLLaqocNu1pAOajQgyMGHMBy%2BKW8%2BhdRPr656jh81KwV%2FcUz%2BX%2Bri0udeRI8iSWR1bewgJdGtMQe3pzSZ1w3V16DAk%2Bi2hTOJXGCdNOLPQjC1GUBKVhdRJTU0uXk9dE8a%2Bn%2Bp2kuMcnRqaXro9Ya%2Ff4U0676v0JwseMng%2FGQp9ehJlbPzwtx5n0H",
                    "protocol": "http"
                },
                "lowQuality": {
                    "bitrate": "32",
                    "encoding": "aacplus",
                    "audioUrl": "http://audio-sv5-t2-1-v4v6.pandora.com/access/226734167372417065.mp4?version=4&lid=1797938999&token=CQ7xvDEck%2FutSGT4CwBfabSJD9DGqEv%2Bl5etfRYIcRtr6aQHd4ske3UE2%2FqzigYDSj6TIFMvq1a13lVZ0wkrCiMwbctJJs%2BhvJ17tqP3A9ul0dtwC0a%2B6wUWZ2h8MX4gC%2B96puCfQBcEH0hgBBlNTn%2F21lc2gGheE1ls6fAfUXa6P%2FoNRYtruiAJ%2Bne99iqzUCVNGl1Tyolgep7izpcdT4k86qVYiSfhTlXG8HatSCco0hkoqgi8JjFG00WXvx1eWJfBdZQ%2B2h9CBArHUbzIqs59BsFo%2Fq4oFOmAm2dVGZjEnZbQURqPpFFU08iw2tZP2t7lrh%2Bpeqvpe9rpz3g%2BQcC13H0vHTyhrD7esVz3ifAVb5IbjE4tSOCWqkuvRTi9",
                    "protocol": "http"
                }
            },
            "adTrackingTokens": [
                "ADU-1797938999-42-232-pod/1/1/0--0-1450700391437",
                "ADU-1797938999-42-232-pod/1/1/0--1-1450700391437"
            ],
            "bannerAdMap": {
                "html": "\n\t\t<!-- xplatformAudioAdWith300x250Banner -->\n\t\t<body style=\"padding:0px;margin-left:0px;margin-right:0px;margin-top:0px;margin-bottom:0px;background-color:transparent;text-align:center\">\n\t\t\t<script type='text/javascript'>\n\t\t\t\tvar withoutBorderWeb = '<a href=\"http://adclick.g.doubleclick.net/aclk?sa=L&ai=BN-k_Zu53Vsr-F8-MlALj2rngAdjY8PcIAAAAEAEgADgAWPiivbTzAmDJBoIBF2NhLXB1Yi0yMTY0NjIyMzg3Njg3ODgysgEYd3d3LmRjbGstZGVmYXVsdC1yZWYuY29tugEJZ2ZwX2ltYWdlyAEJ2gEgaHR0cDovL3d3dy5kY2xrLWRlZmF1bHQtcmVmLmNvbS-YApNYwAIC4AIA6gIhNDIwNC9wYW5kLmFuZHJvaWQvcHJvZC5ub3dwbGF5aW5n-AKB0h6QA6QDmAOkA6gDAeAEAaAGINgHAA&num=0&sig=AOD64_1dqywjcCPaB_sDzcmIjy7yPRJRbQ&client=ca-pub-2164622387687882&adurl=https://www.att.com/shop/wireless/devices/prepaidphones.html\" target=\"_blank\"><img src=\"http://www.pandora.com/util/mediaserverPublicRedirect.jsp?type=file&file=ads/d/2015/12/5/2/7/828725/asset_750814.jpg\" width=\"300\" height=\"250\" border=\"0\" /></a>';\n\t\t\t\t\tvar withoutBorderMobile = withoutBorderWeb;\n\t\t\t\tvar withBorderMobile = '<table width=\"320\" border=\"0\" cellspacing=\"0\" cellpadding=\"0\"><tr><td colspan=\"3\"><img src=\"http://www.pandora.com/static/ads/mobile_300x250_template/shell300x250_01_top.png\" name=\"BorderTop\" width=\"320\" height=\"11\" id=\"BorderTop\" /></td></tr><tr><td width=\"10\"><img src=\"http://www.pandora.com/static/ads/mobile_300x250_template/shell300x250_02_left.png\" name=\"BorderLeft\" width=\"10\" height=\"250\" id=\"BorderLeft\" /></td><td>' + withoutBorderMobile + '</td><td width=\"10\"><img src=\"http://www.pandora.com/static/ads/mobile_300x250_template/shell300x250_04_rght.png\" name=\"BorderRight\" width=\"10\" height=\"250\" id=\"BorderRight\" /></td></tr><tr><td colspan=\"3\"><img src=\"http://www.pandora.com/static/ads/mobile_300x250_template/shell300x250_05_bttm.png\" name=\"BorderBottom\" width=\"320\" height=\"11\" id=\"BorderBottom\" /></td></tr></table>';\n\t\t\t\tif (typeof PandoraApp == \"object\") {\n\t\t\t\t\tvar isIPad =navigator.userAgent.match(/iPad/i);\n\t\t\t\t\tif (isIPad) {\n\t\t\t\t\t\tdocument.write(withoutBorderMobile);\n\t\t\t\t\t\tPandoraApp.setViewportHeight(250);\n\t\t\t\t\t} else {\n\t\t\t\t\t\tdocument.write(withBorderMobile);\n\t\t\t\t\t\tPandoraApp.setViewportHeight(272);\n\t\t\t\t\t}\n\t\t\t\t} else {\n\t\t\t\t\tmedium_rectangle();\n                    if(parent.setActiveStyleSheet) parent.setActiveStyleSheet(\"default\");\n\t\t\t\t\tdocument.write(withoutBorderWeb);\n\t\t\t\t}\n\t\t\t</script>\n\t\t</body>\n                            "
            },
            "companyName": "",
            "trackGain": "0.0",
            "title": ""
        }
    }

.. index::
   pair: method; ad.getAdMetadata

.. _ad-registerAd:

Register advertisement
----------------------

:Method: ad.registerAd

Register the tracking tokens associated with the advertisement. The theory is that this should be done just as the advertisement is about to play.

.. csv-table::
    :header: Name, Type, Description

    stationId, string, The ID of an existing station (see :ref:`station-getStation`) to register the ads against (optional)
    adTrackingTokens, string, The tokens of the ads to register (see :ref:`ad-getAdMetadata`)

.. code:: json

    {
        "stat": "ok"
    }
