Contacts
========

Contacts are people. Companies are not included in the contacts, they have a separate API endpoint.

Json format
-----------

    {
    'id': 4,
	  'cn': 'Busy Bee Ltd.',
		'description': 'basic description',
		'is_company': true,
		'email': ['praveen.bellur@gmail.com', 'praveen@yahoo.com'],
		'phones': [{'type': 'Work', 'no': '008745849854'}, {'type': 'Home', 'no': '87450-94545'}],
		'website': ['http://www.cleverboy.com', 'http://www.clevergirl.com'],
    'address': '200 Marbello Road',
		'city': 'London',
		'postcode': 'SW9 2BR',
		'country': 'United Kingdom',
		'smids': [{'type': 'Twitter', 'smid': 'clevertim'}, {'type': 'Facebook', 'smid': 'mikesperanza'}],
		'ctype': 'C',
		'cf':{'3': '54334', '2': '453'},
		"tags": ["Europe", "twitter", "important"],
		"notes": [2],
		"opportunities": [1],
		"tasks": [2,3],
		"cases": [1,2,3]
    }

Where:
cn = company name
smids = social media ids
cf = list of custom fields in the form { id : value }
ctype = customer type from the list:

	'C' = 'Customer'
	'P'= 'Prospect'
	'S'= 'Supplier'
	'R'= 'Reseller'
	'E'= 'Employee'
	'O'= 'Competitor'
	'N'= 'Consultant'
	'T'= 'Contractor'
	'D'= 'Distributor'
	'X'= 'Influencer'
	'I'= 'Investor'
	'M'= 'Manufacturer'
	'A'= 'Retailer'
	'V'= 'Vendor'
	'W'= 'Wholesaler'
	'L'= 'Lead'
	'F'= 'Friend'
	'H'= 'Other'

notes, opportunities, tasks and cases are read only properties. To update the list, you need to add new notes and set the cust property of the notes (same for opportunities, tasks and cases)
	
Endpoint
--------

    /company

    /company/{id}

Get all companies
-----------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/company

Get a specific company
----------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X https://www.clevertim.com/api/company/1

Add a new company
-----------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X POST -d '{"cn":"My Ltd."}' https://www.clevertim.com/company
	
At a minimum, provide the company name.

Update an existing company
--------------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -H "Content-Type: application/json" -X PUT -d '{"id":367,"cn":"MyLtd."}' https://www.clevertim.com/company/367
	
Delete an existing company
---------------------------

    curl -u AKJHjjsdBNhkdjfdnbsdjfDJKHZ123:X -X DELETE -d '{"id":367,"cn":"MyLtd"}' https://www.clevertim.com/company/367