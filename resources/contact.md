Contacts
========

Contacts are people. Companies are not included in the contacts, they have a separate API endpoint.

Json format
-----------

	{
		"id": 4,
		"fn": "PRAVEEN",
		"ln": "BELLUR",
		"title":"Business Development IT Sales",
		"description": "basic description",
		"is_company": false,
		"companyId": 3,
		"email": ["praveen.bellur@gmail.com", "praveen@yahoo.com"],
		"phones": [{"type": "Work", "no": "008745849854"}, {"type": "Home", "no": "87450-94545"}],
		"website": ["http://www.cleverboy.com", "http://www.clevergirl.com"],
		"address": "200 Marbello Road",
		"city": "London",
		"postcode": "SW9 2BR",
		"country": "United Kingdom",
		"smids": [{"type": "Twitter", "smid": "clevertim"}, {"type": "Facebook", "smid": "mikesperanza"}],
		"ctype": "C",
		"cf":{"3": "54334", "2": "453"},
		"tags": ["Europe", "twitter", "important"],
		"notes": [2],
		"opportunities": [1],
		"tasks": [2,3],
		"cases": [1,2,3]
	}

Where:
fn = first name
ln = last name
companyId = the id of the company this user works for
smids = social media ids
cf = list of custom fields in the form { id : value }
ctype = customer type from the list:

	C = Customer
	P = Prospect
	S = Supplier
	R = Reseller
	E = Employee
	O = Competitor
	N = Consultant
	T = Contractor
	D = Distributor
	X = Influencer
	I = Investor
	M = Manufacturer
	A = Retailer
	V = Vendor
	W = Wholesaler
	L = Lead
	F = Friend
	H = Other

notes, opportunities, tasks and cases are read only properties. To update the list, you need to add new notes and set the cust property of the notes (same for opportunities, tasks and cases)
	
Endpoint
--------

    /contact

    /contact/{id}

Get all contacts
----------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/contact

Get a specific contact
----------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/contact/1

Add a new contact
-----------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X POST -d '{"fn":"Mike"}' https://www.clevertim.com/contact
	
At a minimum, provide either the first name or the last name.

Update an existing contact
--------------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X PUT -d '{"id":367,"fn":"John"}' https://www.clevertim.com/contact/367
	
Delete an existing customer
---------------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -X DELETE -d '{"id":367,"fn":"John"}' https://www.clevertim.com/contact/367

You think there's a better way? Why not contact us and help us improve our [small business CRM](http://www.clevertim.com) API?