========
REST API
========

The Pandora REST API is used by modern Pandora apps including the website and
the various mobile apps provided by Pandora. The current REST API has multiple
versions and not all functionality seems to be supported for each version.
Released API versions are stable but new APIs are added often as the Pandora
feature set evolves. The main endpoint is:

- https://www.pandora.com/api/

All requests are JSON-encoded and sent via HTTP POST body to the endpoints over
HTTPS. Requests require a ``Content-Type`` header of ``application/json``.
Response bodies are JSON-encoded values. Unlike the JSON v5 API there is no
requirement for time syncronization, Blowfish cryptography, or partner logins.

.. toctree::
   :maxdepth: 2

   authentication
   stations
   bookmarks
   account
   ads
   endpoints
   errorcodes
   music
   ondemand
   playlist
   search
   listener

.. _rest-csrf-token:

CSRF Token / Cookie
===================
All requests require an ``X-CsrfToken`` header as well as a matching
``csrftoken`` cookie. The current version of the API merely validates that the
token and cookie match so the client can make up whatever they want. However,
the token can also be obtained by making a ``HEAD`` request to
``https://www.pandora.com/`` and saving the cookies. The API endpoints will not
serve cookies until after authentication. Clients *SHOULD* make a ``HEAD``
request to the root domain and include the current value of the ``csrftoken``
cookie in each request.

.. code:: http

    POST /api/v1/auth/login HTTP/1.1
    Host: www.pandora.com
    Content-Type: application/json;charset=utf-8
    X-CsrfToken: 123456a7889b1c23
    X-AuthToken: 

    { "username": "foo", "password": "bar" }

.. _rest-auth-token:

Auth Token
==========
All requests except for login require an ``X-AuthToken`` header which contains
the auth token obtained during login. It is acceptable to include the
``X-AuthToken`` header with an empty value during login.

.. code:: http

    POST /api/v1/station/getStations HTTP/1.1
    Host: www.pandora.com
    Content-Type: application/json;charset=utf-8
    X-CsrfToken: 123456a7889b1c23
    X-AuthToken: dGhpcyBpcyBqdXN0IGFuIGV4YW1wbGUgY29kZQo=

    { "pageSize": 250 }

Errors
======
Error conditions are indicated by a combination of HTTP status code and a JSON
response body. Any responses with a 200 status code are successful.

.. code:: json

    {
        "errorCode": 0,
        "errorString": "INVALID_REQUEST",
        "message": "The request could not be validated"
    }
