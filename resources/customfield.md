Custom fields
=============

Custom fields are additional fields that you can define for your contacts, companies, opportunities and cases.
They give you the extra power and allow you to customize Clevertim with the additional data that you need.
Clevertim.com custom fields are typed and can be of the following types:

- input  	- simple input, no validation
- select	- a dropdown with values you can define
- date		- a date picker control
- user		- dropdown to choose from your existing users
- state		- dropdown to choose from a list of US states
- country	- dropdown to choose from a list of countries

Json format
-----------

	{
		"id": 1
		"elemType": "date",
		"name": "Deadline",
		"modelType": ["cases", "opportunities"],
		"values": ["X", "Y", "Z"]
	}

Where:

- elemType is the type of the custom field control, as described above: input, select, date, user, state, country
- name is the name of the field as it is displayed to the users
- modelType is a list of models/views where this control is displayed (it is applicable to): customers, companies, cases, opportunities
- values (only present for elemType:"select") is a list of values to be defined by the user

Endpoint
--------

    /customfield

    /customfield/{id}

Get all custom fields
---------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/customfield

Get a specific custom field
---------------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/customfield/1

Add a new custom field
----------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X POST -d '{"elemType":"date","name":"Deadline","modelType":["cases"]}' https://www.clevertim.com/customfield
	
Update an existing custom field
-------------------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X PUT -d '{"id":367,"elemType":"date","name":"Deadline","modelType":["cases"]}' https://www.clevertim.com/customfield/367
	
Delete an existing custom field
-------------------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -X DELETE -d '{"id":367}' https://www.clevertim.com/customfield/367

Do you like our [small business CRM](http://www.clevertim.com) API? Please help us spread the word!
