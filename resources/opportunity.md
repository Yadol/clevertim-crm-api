Opportunities
=============

These are sales opportunities objects. In other CRM systems they are referred to as "deals".

Json format
-----------

    {
		"id": 1,
		"name": "opportunity 1",
		"description": "this is the description"
		"status": "Won",
		"leadUser": 4,
		"value": "4500",
		"currency": "EUR",
		"cf": {"1": "2012-11-30"},
		"cust": 4,
		"tags": ["sale"],
		"tasks": [3],
		"notes": [6, 2, 1]
    }


status = opportunity status: Open, Closed, Won, Lost - these values are customizable by the users, so they could be different
cf = list of custom fields in the form { id : value }

notes and tasks are read only properties. To update the list, you need to add new notes and set the opportunity property of the notes (same for tasks)
	
Endpoint
--------

    /opportunity

    /opportunity/{id}

Get all opportunities
---------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/opportunity

Get a specific opportunity
--------------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/opportunity/1

Add a new opportunity
---------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X POST -d '{"name":"Sell more"}' https://www.clevertim.com/opportunity
	
At a minimum, provide the opportunity name.

Update an existing opportunity
------------------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X PUT -d '{"id":367,"name":"Sell much more"}' https://www.clevertim.com/opportunity/367
	
Delete an existing opportunity
------------------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -X DELETE -d '{"id":367,"fn":"Sell much more"}' https://www.clevertim.com/opportunity/367

Need help? Send us your questions, we'll answer them and also use those questions to improve our [small business CRM](http://www.clevertim.com) API.