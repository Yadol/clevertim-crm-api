Tasks
=====

Json format
-----------

	{
		"id": 3,
		"name": "send them a new email",
		"location": "London",
		"case": 1,
		"startDate": {"y": 2013, "mo": 12, "d": 29, "h": 4, "mi": 4},
		"endDate": {"y": 2013, "mo": 12, "d": 31, "h": 7,  "mi": 5},
		"cust": 10,
		"aUserId": 2,
		"is_deleted": false,
		"is_completed": false,
		"atype": "TO DO",
		"comments": [1,3],
		"opp": 2,
	}

case, opp and cust are the ids of the case, opportunity and customer respectively, that this note is attached to.
aUserId is the id of the assigned user.
atype is the type of the task: Email, TO DO, Meeting, Not set, Call, Follow up

Endpoint
--------

    /task

    /task/{id}

Get all tasks
-------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/task

Get a specific task
-------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/task/1

Add a new task
--------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X POST -d '{"name":"New task"}' https://www.clevertim.com/task

Update an existing task
-----------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X PUT -d '{"id":367,"name":"New task 2"}' https://www.clevertim.com/task/367
	
Deleting or marking a task as completed can be done by setting the is_deleted and is_completed properties to true when updating.

Delete an existing task
-----------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -X DELETE -d '{"id":367,"name":"New task 2"}' https://www.clevertim.com/task/367
    
Would you like to see an improved [small business CRM](http://www.clevertim.com) API? Send us your ideas.