Clevertim CRM API
=================

Clevertim.com is an easy to use, easy to learn, [web based small business CRM](http://www.clevertim.com). This API allows users to connect and access their CRM data programatically.
The API follows the REST priciples where each resource has its own URL (e.g.: http://www.clevertim.com/api/contact/3) and it is manipulated via the four HTTP verbs: GET, POST, PUT and DELETE.

The input and output data is in JSON format.
Throughout this documentation, curl is used to exemplify the API usage.

API Endpoints
=============

- [Contacts](https://github.com/clevertim/clevertim-crm-api/blob/master/resources/contact.md)
- [Companies](https://github.com/clevertim/clevertim-crm-api/blob/master/resources/company.md)
- [Cases](https://github.com/clevertim/clevertim-crm-api/blob/master/resources/case.md)
- [Opportunities](https://github.com/clevertim/clevertim-crm-api/blob/master/resources/opportunity.md)
- [Tasks](https://github.com/clevertim/clevertim-crm-api/blob/master/resources/task.md)
- [Notes](https://github.com/clevertim/clevertim-crm-api/blob/master/resources/note.md)
- [Comments](https://github.com/clevertim/clevertim-crm-api/blob/master/resources/comment.md)
- [Custom fields](https://github.com/clevertim/clevertim-crm-api/blob/master/resources/customfield.md)

Authorization
=============

The API authorization is at the user level, each access is done via an existing user. There is no special API user.
The entitlements of the user accessing the API will be applied. As such, if the user has read-only access, writing via the API will fail.

Authentication
==============

The authentication of the user running the API is done via an API token. You can generate and view your token in the Account/My Info & Settings section, once you are logged into your Clevertim account.
The authentication token should not be shared under any circumstances. Keep in mind: whoever has access to your token, has access to your data.
If you suspect your token might have been compromised, you can re-generate it in the Account/My Info & Settings section.

When you use the token, Clevertim doesn't require a password, but since some implementations of the HTTP Basic Authentication assume there is always a password, you can just pass an X for convenience. Here's an authentication example:

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/contact

To protect your token from being "sniffed" in transit, the use of https is recommended. Only use the APIs over http at your own risk.

Reading data
============

Reading data is done via GET requests. Clevertim currently supports two types of requests: read one entry and read all entries.

Here's an example that reads all the companies:

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/company

And here is an example that reads a specific company:

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/company/3423

If the request is successful, you will get status code 200 and a json object representing the results. The json object for successful requests will look like this:

    {
        "status": "OK",
        "content": [ obj1, obj2, ...]
    }

If the request results in an error, the json object will look like this:

    {
        "status": "ERROR",
        "error": "Message describing the error here"
    }

Writing data
============

Writing data is done via the other HTTP verbs as follows:

- POST   - for adding a new element
- PUT    - for updating an existing element
- DELETE - for deleting an existing element

Adding a new case
-----------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X POST -d '{"name":"New case"}' https://www.clevertim.com/case

On success, the response["content"] will contain a single element in the list, the new element. The element will have a property 'id' which identifies the object and which you can use in edits and deletes.

Editing an existing case
------------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X PUT -d '{"name":"New case 2"}' https://www.clevertim.com/case/367

On success, the response["content"] will contain a single element in the list, with the updated values for its properties.

Deleting an existing case
-------------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -X DELETE -d '{"name":"New case 2"}' https://www.clevertim.com/case/367

On success, the response object will not have any content, only a status: "OK".

Failures and errors
===================

Any failures and errors will be reflected in the HTTP status code. The 200 status code indicates success, anything else means failure.
You can see the following HTTP status codes:

- 200 - SUCCESS, inspect the content
- 404 - Error, The object you are trying to get, update or delete cannot be found
- 400 - Error, Bad request, inspect the "error" property of the content to understand more about the specific error
- 500 - Error, your JSON cannot be parsed. Use a json syntax validator
- 501 - Error, operation not supported

Help us improve the API
=======================

Please reach out to us with any feedback or suggestions for improvements. Either message us on github, contact us at [clevertim.com](http://www.clevertim.com).
We will post updates here and on our [CRM blog](http://blog.clevertim.com).

