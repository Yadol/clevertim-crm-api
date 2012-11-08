Comments
========

Json format
-----------

    {
        'comment': 'this is a new comment',
        'nid': 3,
        'tid': null
    }

nid is the id of the note this comment is attached to.
tid is the id of the task this comment is attached to
Only one of them can be populated, as a comment can only be attached to either a note or a task, not both.

Endpoint
--------

    /comment

    /comment/{id}

Get all comments
----------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/comment

Get a specific comment
----------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/comment/1

Add a new comment
-----------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X POST -d '{"name":"New comment", "tid":1}' https://www.clevertim.com/comment

Update an existing comment
--------------------------

This is not supported.
Use delete/create if you need to update a comment.

Delete an existing comment
--------------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -X DELETE -d '{"id":1}' https://www.clevertim.com/comment/3

Ran into problems? We're always looking for feedback and suggestions on how to make our [small business CRM](http://www.clevertim.com) API easier to use.