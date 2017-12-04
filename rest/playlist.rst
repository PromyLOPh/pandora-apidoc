.. _rest-playlist:

========
Playlist
========

.. _rest-v1-playlist-getFragment:

Get Fragment
============

:Endpoint: /v1/playlist/getFragment

Request
-------
.. code:: json

  {
    "stationId": "3793312577613735337",
    "isStationStart": true,
    "fragmentRequestReason": "Normal",
    "audioFormat": "aacplus",
    "startingAtTrackId": null,
    "onDemandArtistMessageArtistUidHex": null,
    "onDemandArtistMessageIdHex": null
  }

Response
--------
.. code:: json

  {
    "tracks": [
      {
        "userSeed": "G1473",
        "genre": [
          "Rock"
        ],
        "monthlyListening": 0,
        "listeningTimestamp": "1512414066099",
        "shareLandingURL": "https://www.pandora.com/niall-horan/slow-hands-single/slow-hands/TRXgqVhPXtj3k9g?shareImp=true",
        "isSeed": false,
        "allowStartStationFromTrack": true,
        "allowShareTrack": true,
        "allowBuyTrack": true,
        "allowTiredOfTrack": true,
        "allowSkipTrackWithoutLimit": false,
        "allowSkip": true,
        "allowFeedback": true,
        "composerName": "",
        "artistSeoToken": "niall-horan/AR3cxZc3P2dllcq",
        "albumSeoToken": "niall-horan/slow-hands-single/ALjcm3n766qqcKZ",
        "isCompilation": false,
        "amazonUrl": "https://www.amazon.com/gp/search/?index=music&field-artist=Niall+Horan&field-title=Slow+Hands+%28Single%29&tag=wwwpandoracom-20",
        "amazonDigitalAsin": "B071KHGZVJ",
        "albumAmazonDigitalAsin": "B072KQKMRL",
        "itunesUrl": "https://itunes.apple.com/album/slow-hands/id1230745029?i=1230745661&uo=5&at=11l3Hh&app=itunes",
        "isFeatured": false,
        "isBookmarked": false,
        "adUrls": {
          "flexSkipAdUrl": "https://adserver.pandora.com/haymaker/api/v1/serve/?slot=FLEX_SKIP&targeting=a11%3D10,15,22,27,6%3Baa%3D0%3Bab%3D100,120,122,125,129,131,133,136,137,140,141,144,146,148,151,154,156,158,163,62,69,72,88%3Bag%3D24%3Bapp%3D%3Bclean%3D0%3Bco%3D18039%3Bcon%3D%3Bd1%3D3%3Bd2%3D73%3Bd3%3D154%3Bd4%3D1748,1750,1881%3Bd8%3D0%3Bdma%3D588%3Bet%3D2%3Bfam%3D-1%3Bgcat%3DG1473%3Bgenre%3Dlatin%3Bgnd%3D1%3Bhhi%3D0%3Bhisp%3D0%3Bhours%3D0%3Bindex%3D__INDEX__%3Binteraction%3Dskip_limit%3Bmc%3D%3Bmodel%3D%3Bmsa%3D%3Bp%3D1,103,110,116,13,135,140,158,21,260,31,33,37,4,533,551,570,578,585,655,667,677,8,964%3Bp13%3D2%3Bp8%3D2%3Bst%3DIN%3Bstation%3D%3Bt4%3D257,334,335,337,358,363,396,398,447,469,491,508,514,556,562,565,573,591,592,600,613,614,673,690,696,709,778,796,804,847,848,857,858,906%3Buq%3Dbf756e84b44d3c48c4b2fc493aa56950%3Bvx%3D%3Bzip%3D46516&l=joa5tbfs7a2n4nczsl7tilo4nhtest7atn4rdri&zone=prod.__ZONE__&site=default&env=prod&assetType=COACHMARK&ppid=bf756e84b44d3c48c4b2fc493aa56950&c=__CACHEBUST__",
          "flexReplayAdUrl": "https://adserver.pandora.com/haymaker/api/v1/serve/?slot=FLEX_REPLAY&targeting=a11%3D10,15,22,27,6%3Baa%3D0%3Bab%3D100,120,122,125,129,131,133,136,137,140,141,144,146,148,151,154,156,158,163,62,69,72,88%3Bag%3D24%3Bapp%3D%3Bclean%3D0%3Bco%3D18039%3Bcon%3D%3Bd1%3D3%3Bd2%3D73%3Bd3%3D154%3Bd4%3D1748,1750,1881%3Bd8%3D0%3Bdma%3D588%3Bet%3D2%3Bfam%3D-1%3Bgcat%3DG1473%3Bgenre%3Dlatin%3Bgnd%3D1%3Bhhi%3D0%3Bhisp%3D0%3Bhours%3D0%3Bindex%3D__INDEX__%3Binteraction%3Dreplay%3Bmc%3D%3Bmodel%3D%3Bmsa%3D%3Bp%3D1,103,110,116,13,135,140,158,21,260,31,33,37,4,533,551,570,578,585,655,667,677,8,964%3Bp13%3D2%3Bp8%3D2%3Bst%3DIN%3Bstation%3D%3Bt4%3D257,334,335,337,358,363,396,398,447,469,491,508,514,556,562,565,573,591,592,600,613,614,673,690,696,709,778,796,804,847,848,857,858,906%3Buq%3Dbf756e84b44d3c48c4b2fc493aa56950%3Bvx%3D%3Bzip%3D46516&l=5bweg5xwsbe2vaed6kw5ujas4q5viuxyjfrzyyq&zone=prod.__ZONE__&site=default&env=prod&assetType=COACHMARK&ppid=bf756e84b44d3c48c4b2fc493aa56950&c=__CACHEBUST__",
          "flexThumbsDownAdUrl": "https://adserver.pandora.com/haymaker/api/v1/serve/?slot=FLEX_THUMBS_DOWN&targeting=a11%3D10,15,22,27,6%3Baa%3D0%3Bab%3D100,120,122,125,129,131,133,136,137,140,141,144,146,148,151,154,156,158,163,62,69,72,88%3Bag%3D24%3Bapp%3D%3Bclean%3D0%3Bco%3D18039%3Bcon%3D%3Bd1%3D3%3Bd2%3D73%3Bd3%3D154%3Bd4%3D1748,1750,1881%3Bd8%3D0%3Bdma%3D588%3Bet%3D2%3Bfam%3D-1%3Bgcat%3DG1473%3Bgenre%3Dlatin%3Bgnd%3D1%3Bhhi%3D0%3Bhisp%3D0%3Bhours%3D0%3Bindex%3D__INDEX__%3Binteraction%3Dskip_limit%3Bmc%3D%3Bmodel%3D%3Bmsa%3D%3Bp%3D1,103,110,116,13,135,140,158,21,260,31,33,37,4,533,551,570,578,585,655,667,677,8,964%3Bp13%3D2%3Bp8%3D2%3Bst%3DIN%3Bstation%3D%3Bt4%3D257,334,335,337,358,363,396,398,447,469,491,508,514,556,562,565,573,591,592,600,613,614,673,690,696,709,778,796,804,847,848,857,858,906%3Buq%3Dbf756e84b44d3c48c4b2fc493aa56950%3Bvx%3D%3Bzip%3D46516&l=fywri4r7i35owrp4hs3v6ztzt5nulofdaepntry&zone=prod.__ZONE__&site=default&env=prod&assetType=COACHMARK&ppid=bf756e84b44d3c48c4b2fc493aa56950&c=__CACHEBUST__",
          "nowPlayingStationAdUrl": "https://pubads.g.doubleclick.net/gampad/adx?iu=/4204/pand.default/prod.radio&t=a11%3D10,15,22,27,6%26aa%3D0%26ab%3D100,120,122,125,129,131,133,136,137,140,141,144,146,148,151,154,156,158,163,62,69,72,88%26abx%3D654,1454,983,487,484,632,985,448,631,1431,1289,424,485,646,1193,1412,1158,402,989,1156,906,907,1414,429,984,1118,1159%26ag%3D24%26artist%3DG1473%26async%3D0%26clean%3D0%26co%3D18039%26comped%3D0%26d1%3D3%26d2%3D73%26d3%3D154%26d4%3D1748,1750,1881%26d8%3D0%26dma%3D588%26dse%3D0%26et%3D2%26exp%3D0%26fam%3D-1%26fb%3D0%26gcat%3DG1473%26gnd%3D1%26hhi%3D0%26hisp%3D0%26hours%3D0%26iat%3D0%26index%3D__INDEX__%26interaction%3D__ACTION__%26l%3Dhvy5cswdlmirfmg5lrj5tw2qw2kgfjopmkutnqy%26p%3D1,103,110,116,13,135,140,158,21,260,31,33,37,4,533,551,570,578,585,655,667,677,8,964%26p13%3D2%26p8%3D2%26prg%3D1%26st%3DIN%26t4%3D257,334,335,337,358,363,396,398,447,469,491,508,514,556,562,565,573,591,592,600,613,614,673,690,696,709,778,796,804,847,848,857,858,906%26uq%3Dbf756e84b44d3c48c4b2fc493aa56950%26zip%3D46516&ppid=bf756e84b44d3c48c4b2fc493aa56950&sz=2000x2%7C300x250%7C300x600&c=__CACHEBUST__",
          "nowPlayingStationAdUnit": "/4204/pand.default/prod.radio",
          "nowPlayingStationAdTargeting": "a11=10,15,22,27,6;aa=0;ab=100,120,122,125,129,131,133,136,137,140,141,144,146,148,151,154,156,158,163,62,69,72,88;abx=654,1454,983,487,484,632,985,448,631,1431,1289,424,485,646,1193,1412,1158,402,989,1156,906,907,1414,429,984,1118,1159;ag=24;artist=G1473;async=0;clean=0;co=18039;comped=0;d1=3;d2=73;d3=154;d4=1748,1750,1881;d8=0;dma=588;dse=0;et=2;exp=0;fam=-1;fb=0;gcat=G1473;gnd=1;hhi=0;hisp=0;hours=0;iat=0;index=__INDEX__;interaction=__ACTION__;l=hvy5cswdlmirfmg5lrj5tw2qw2kgfjopmkutnqy;p=1,103,110,116,13,135,140,158,21,260,31,33,37,4,533,551,570,578,585,655,667,677,8,964;p13=2;p8=2;prg=1;st=IN;t4=257,334,335,337,358,363,396,398,447,469,491,508,514,556,562,565,573,591,592,600,613,614,673,690,696,709,778,796,804,847,848,857,858,906;uq=bf756e84b44d3c48c4b2fc493aa56950;zip=46516",
          "backstageAdUrl": "https://pubads.g.doubleclick.net/gampad/adx?iu=/4204/pand.default/prod.backstage&t=a11%3D10,15,22,27,6%26aa%3D0%26ab%3D100,120,122,125,129,131,133,136,137,140,141,144,146,148,151,154,156,158,163,62,69,72,88%26abx%3D654,1454,983,487,484,632,985,448,631,1431,1289,424,485,646,1193,1412,1158,402,989,1156,906,907,1414,429,984,1118,1159%26ag%3D24%26artist%3DG1473%26async%3D0%26clean%3D0%26co%3D18039%26comped%3D0%26d1%3D3%26d2%3D73%26d3%3D154%26d4%3D1748,1750,1881%26d8%3D0%26dma%3D588%26dse%3D0%26et%3D2%26exp%3D0%26fam%3D-1%26fb%3D0%26gcat%3DG1473%26gnd%3D1%26hhi%3D0%26hisp%3D0%26hours%3D0%26iat%3D0%26index%3D__INDEX__%26interaction%3D__ACTION__%26l%3Duhymlajwxw3z4lp4d2novvuiivbwfgqqgtf6dqq%26p%3D1,103,110,116,13,135,140,158,21,260,31,33,37,4,533,551,570,578,585,655,667,677,8,964%26p13%3D2%26p8%3D2%26prg%3D1%26st%3DIN%26t4%3D257,334,335,337,358,363,396,398,447,469,491,508,514,556,562,565,573,591,592,600,613,614,673,690,696,709,778,796,804,847,848,857,858,906%26uq%3Dbf756e84b44d3c48c4b2fc493aa56950%26zip%3D46516&ppid=bf756e84b44d3c48c4b2fc493aa56950&sz=2000x2%7C300x250%7C300x600&c=__CACHEBUST__",
          "backstageAdUnit": "/4204/pand.default/prod.backstage",
          "backstageAdTargeting": "a11=10,15,22,27,6;aa=0;ab=100,120,122,125,129,131,133,136,137,140,141,144,146,148,151,154,156,158,163,62,69,72,88;abx=654,1454,983,487,484,632,985,448,631,1431,1289,424,485,646,1193,1412,1158,402,989,1156,906,907,1414,429,984,1118,1159;ag=24;artist=G1473;async=0;clean=0;co=18039;comped=0;d1=3;d2=73;d3=154;d4=1748,1750,1881;d8=0;dma=588;dse=0;et=2;exp=0;fam=-1;fb=0;gcat=G1473;gnd=1;hhi=0;hisp=0;hours=0;iat=0;index=__INDEX__;interaction=__ACTION__;l=uhymlajwxw3z4lp4d2novvuiivbwfgqqgtf6dqq;p=1,103,110,116,13,135,140,158,21,260,31,33,37,4,533,551,570,578,585,655,667,677,8,964;p13=2;p8=2;prg=1;st=IN;t4=257,334,335,337,358,363,396,398,447,469,491,508,514,556,562,565,573,591,592,600,613,614,673,690,696,709,778,796,804,847,848,857,858,906;uq=bf756e84b44d3c48c4b2fc493aa56950;zip=46516"
        },
        "songTitle": "Slow Hands",
        "musicId": "S10296263",
        "trackType": "Track",
        "pandoraId": "TR:10296263",
        "trackToken": "PTlqhbC-55drVs1yFGsa4D5UPmVsZ9z-F1Oa1wNdpYk2_Q0RDUKG3_U3vDcuVW3DPa8Lf2OA5ToR4nulgKysBkw",
        "identity": "41561d0348209a43fd397f2baa1b41ad",
        "trackLength": 188,
        "rating": 0,
        "stationId": "3793312577613735337",
        "fileGain": "-3.75",
        "songDetailURL": "https://www.pandora.com/artist/niall-horan/slow-hands-single/slow-hands/TRXgqVhPXtj3k9g",
        "trackSeoToken": "niall-horan/slow-hands-single/slow-hands/TRXgqVhPXtj3k9g",
        "audioURL": "https://audio-ch1-t1-2-v4v6.pandora.com/access/?version=5&lid=112207273&token=yxyJ0D%2FlHwnMbB57N28oKHX1sPFTQnipfbm684tmEwdU%2F41wUlQRlBThmBzkSmT3PXzMWRcq2XDnttLJqd3ORPvfmmpzoiMlTZ2mGogkZugzyMm6YBFNSlDXZkige4m6xhrbrj95OWs9rbYl8MM4jMoQ4NmO7erq4rqo96wIFqUQRJh82jOzKvCEcE1wVn0IUOFipusC9G%2BCQyP4O8%2BO7ZoMfyqUJ%2Fcd5tbP5VzuyIyVNM%2BqS4dDhM1U82ZNsBVpr5WWzO0kFHD5EnMiY9CmexeVqu5C6ikpkl9Z46r9sSWzsASHlQl9FkQ5IIQ64YYIyebVYbhpWAXUjqoK4pOA8A%3D%3D",
        "rights": [
          "replayRequiresReward",
          "allowSkipAfterLimit",
          "showReplayButton",
          "allowReplay"
        ],
        "audioEncoding": "aacplus",
        "audioTokenId": "jp6ta2492",
        "audioReceiptURL": "https://audio-ch1-t1-2-v4v6.pandora.com/receipt/?version=5&receiptId=yxyJ0D%2FlHwnRoreL923tJg9zb%2BZz9reD&token=yxyJ0D%2FlHwnMbB57N28oKHX1sPFTQnipfbm684tmEwdU%2F41wUlQRlBThmBzkSmT3PXzMWRcq2XDnttLJqd3ORPvfmmpzoiMlTZ2mGogkZugzyMm6YBFNSlDXZkige4m6xhrbrj95OWs9rbYl8MM4jMoQ4NmO7erq4rqo96wIFqUQRJh82jOzKvCEcE1wVn0IUOFipusC9G%2BCQyP4O8%2BO7ZoMfyqUJ%2Fcd5tbP5VzuyIyVNM%2BqS4dDhM1U82ZNsBVpr5WWzO0kFHD5EnMiY9CmexeVqu5C6ikpkl9Z46r9sSWzsASHlQl9FkQ5IIQ64YYIyebVYbhpWAXUjqoK4pOA8A%3D%3D",
        "audioSkipUrl": "https://audio-ch1-t1-2-v4v6.pandora.com/skip/?version=5&token=yxyJ0D%2FlHwnMbB57N28oKHX1sPFTQnipfbm684tmEwdU%2F41wUlQRlBThmBzkSmT3PXzMWRcq2XDnttLJqd3ORPvfmmpzoiMlTZ2mGogkZugzyMm6YBFNSlDXZkige4m6xhrbrj95OWs9rbYl8MM4jMoQ4NmO7erq4rqo96wIFqUQRJh82jOzKvCEcE1wVn0IUOFipusC9G%2BCQyP4O8%2BO7ZoMfyqUJ%2Fcd5tbP5VzuyIyVNM%2BqS4dDhM1U82ZNsBVpr5WWzO0kFHD5EnMiY9CmexeVqu5C6ikpkl9Z46r9sSWzsASHlQl9FkQ5IIQ64YYIyebVYbhpWAXUjqoK4pOA8A%3D%3D",
        "artistName": "Niall Horan",
        "artistMusicId": "R713137",
        "artistArt": [
          {
            "url": "https://mediaserver-cont-sv5-2-v4v6.pandora.com/images/public/rovi/portrait/7/4/5/4/MN0002854547_200W.jpg",
            "size": 200
          },
          {
            "url": "https://mediaserver-cont-dc6-1-v4v6.pandora.com/images/public/rovi/portrait/7/4/5/4/MN0002854547_640W.jpg",
            "size": 640
          },
          {
            "url": "https://mediaserver-cont-sv5-3-v4v6.pandora.com/images/public/rovi/portrait/7/4/5/4/MN0002854547.jpg",
            "size": 1080
          }
        ],
        "artistDetailURL": "https://www.pandora.com/artist/niall-horan/AR3cxZc3P2dllcq",
        "albumTitle": "Slow Hands (Single)",
        "albumArt": [
          {
            "url": "https://mediaserver-cont-ch1-1-v4v6.pandora.com/images/public/int/9/7/2/1/00602557661279_90W_90H.jpg",
            "size": 90
          },
          {
            "url": "https://cont-1.p-cdn.com/images/public/int/9/7/2/1/00602557661279_130W_130H.jpg",
            "size": 130
          },
          {
            "url": "https://mediaserver-cont-dc6-2-v4v6.pandora.com/images/public/int/9/7/2/1/00602557661279_500W_500H.jpg",
            "size": 500
          },
          {
            "url": "https://mediaserver-cont-ch1-1-v4v6.pandora.com/images/public/int/9/7/2/1/00602557661279_640W_640H.jpg",
            "size": 640
          },
          {
            "url": "https://cont-1.p-cdn.com/images/public/int/9/7/2/1/00602557661279_1080W_1080H.jpg",
            "size": 1080
          }
        ],
        "albumDetailURL": "https://www.pandora.com/artist/niall-horan/slow-hands-single/ALjcm3n766qqcKZ",
        "trackKey": {
          "trackId": "S10296263",
          "trackType": "Track",
          "spinId": "3f3366e3-7775-44bc-b5d9-c363c9d865ed"
        }
      }
    ],
    "listenerQualifiesForUpsell": true,
    "isBingeSkipping": false
  }
