Cases
=====

Json format
-----------

    {
        "id": 1,
        "name": "Case 1",
        "description": "this is an example of a case",
        "tasks": [3, 2],
        "tags": ["case", "support", "open"],
        "notes": [4, 3],
        "leadUser": 5,
        "cf": {"1": "2012-11-22"},
        "cust": 34
    }

The ids above point to the respective tasks, notes, customer and custom fields associated with the case.

Endpoint
--------

    /case

    /case/{id}

Get all cases
-------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/case

Get a specific case
-------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/case/1

Add a new case
--------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X POST -d '{"name":"New case"}' https://www.clevertim.com/case

Update an existing case
-----------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X PUT -d '{"name":"New case 2"}' https://www.clevertim.com/case/367

Delete an existing case
-----------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -X DELETE -d '{"name":"New case 2"}' https://www.clevertim.com/case/367
    

Find it difficult to use the API?
Help us improve our [small business CRM](http://www.clevertim.com) API by sending us your feedback and suggestions.
