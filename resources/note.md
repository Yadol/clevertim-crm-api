Notes
=====

Notes represent capture all your communication with your customers, leads, vendors, suppliers, etc.
Notes can be attached to contacts, companies, cases and opportunities.

Json format
-----------

    {
		"id": 2,
		"desc": "One more note just to make it clear.\n\nTell me more about this."
		"cust": 2,
		"case": 1,
		"opportunity": 2,
		"comments": [1,5]
    }

Endpoint
--------

    /note

    /note/{id}

Get all notes
-------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/note

Get a specific note
-------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/note/1

Add a new note
--------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X POST -d '{"desc":"This is a note"}' https://www.clevertim.com/note
	
Update an existing note
-----------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X PUT -d '{"id":367,"name":"Another note"}' https://www.clevertim.com/note/367
	
Delete an existing note
-----------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -X DELETE -d '{"id":367,"fn":"Sell much more"}' https://www.clevertim.com/note/367

Are you using our [small business CRM](http://www.clevertim.com) API? Tell us about your experience!