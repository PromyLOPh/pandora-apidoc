===================
List of Error Codes
===================

.. index::
   single: REST Error codes

.. note::

    This page is incomplete. The error enumeration should be complete but codes
    and descriptions are guesses.

These error codes can be returned by all endpoints:

.. code:: json

	{
		"errorCode": 0,
		"errorString": "INVALID_REQUEST",
		"message": "The request could not be validated"
	}

==========     =============================    ===========
Error Code     Error String                     Description
==========     =============================    ===========
0              INVALID_REQUEST                  General bad request error. Often means authentication was invalid
1001           INVALID_REQUEST                  Invalid auth token
?              STREAM_VIOLATION                 Unable to stream to this region?
?              STATION_LIMIT_REACHED            Stream minutes limit or skip count reached?
?              THUMBPRINT_RADIO_NOT_ELIGIBLE    Not enough feedback to construct a Thumbprint station?
?              LISTENER_NOT_AUTHORIZED          Current user is not able to access shared content?
?              PLAYLIST_END                     End of playlist?
?              READONLY_MODE                    Pandora back-end maintenance?
?              STATION_CODE_INVALID             Invalid station
?              STATION_DOES_NOT_EXIST           Station does not exist
?              LISTENER_SUSPENDED               Account has been suspended
?              CREDIT_CARD_NO_RECORD_FOUND      No credit card on file?
?              CONTENT_HAS_EXPIRED              Audio link for song has expired?
?              SERVER_ERROR                     Generic server error
?              NOT_FOUND                        Content not found
?              UNPLAYABLE_SHUFFLE_STATION       Unable to play shuffle station?
99000          PLAYLIST_VERSION_MISMATCH        "An operation on a playlist is trying to be made on a version that's different from the most current one." - raised by the v7 playlist APIs.
99003          PLAYLIST_BAD_RANGE               "Invalid range detected when moving/deleting/requesting playlist items." - raised by the v7 playlist APIs.
99022          INVALID_PANDORA_TYPE             "The type of the supplied Pandora ID is invalid for this API endpoint." - mainly raised by the v6 collection APIs.
==========     =============================    ===========
