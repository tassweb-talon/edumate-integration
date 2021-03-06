**SetParents**
----
	Returns "success" and a count of updated and/or failed parent(s), or a structure of invalid validations "__invalid" belonging to parent(s).

* **Version History:**

    TASS v53.2.nnn - Method Added.

* **Version:**

	2
    
* **Method:**

	`GET | POST`
	
*  **Params:**

	**Required:**
 
	`id [string]` - Parent Code sourced from Edumate.

	`surname [string]` - Surname.

	`p1_surname [string]` - Parent 1 Surname. Must not be empty string when any of the other 'p1_' prefixed items are supplied.  If empty string is provided, the person will be removed from the parent in TASS.

	`p1_first_name [string]` - Parent 1 First Name. Must not be empty string when any of the other 'p1_' prefixed items are supplied.  If empty string is provided, the person will be removed from the parent in TASS.

	`p1_preferred_name [string]` - Parent 1 Preferred Name. Must not be empty string when any of the other 'p1_' prefixed items are supplied.  If empty string is provided, the person will be removed from the parent in TASS.  If empty string and `p1_first_name` is supplied, then it is defaulted to `p1_first_name`

	`p1_gender [string]` - Parent 1 Gender. Must not be empty string when any of the 'p1_' prefixed items are supplied. Must be a valid Gender code within TASS.web.  If empty string is provided, the person will be removed from the parent in TASS.

	`p1_occupation [string]` - Parent 1 Occupation.  Must be a valid Occupation description within TASS.web.  If empty string is provided, the person will be removed from the parent in TASS.

	`p1_title [string]` - Parent 1 Title. Must be a valid Salutation within TASS.web.  If empty string is provided, the person will be removed from the parent in TASS.

	`p1_initials [string]` - Parent 1 Initials.  If empty string is provided, the person will be removed from the parent in TASS.

	`p1_other_name [string]` - Parent 1 Other Name.  If empty string is provided, the person will be removed from the parent in TASS.

	`p1_suffix [string]` - Parent 1 Suffix.  If empty string is provided, the person will be removed from the parent in TASS.

	`p2_surname [string]` - Parent 2 Surname. Must not be empty string when any of the 'p2_' prefixed items are supplied.  If empty string is provided, the person will be removed from the parent in TASS.

	`p2_first_name [string]` - Parent 2 First Name. Must not be empty string when any of the 'p2_' prefixed items are supplied.  If empty string is provided, the person will be removed from the parent in TASS.

	`p2_preferred_name [string]` - Parent 2 Preferred Name. Must not be empty string when any of the 'p2_' prefixed items are supplied.  If empty string is provided, the person will be removed from the parent in TASS. If empty string and `p2_first_name` is supplied, then it is defaulted to `p2_first_name`

	`p2_gender [string]` - Parent 2 Gender. Must not be empty string when any of the 'p2_' prefixed items are supplied. Must be a valid Gender code within TASS.web.  If empty string is provided, the person will be removed from the parent in TASS.

	`p2_occupation [string]` - Parent 2 Occupation. Must be a valid Occupation description within TASS.web.  If empty string is provided, the person will be removed from the parent in TASS.

	`p2_title [string]` - Parent 2 Title. Must be a valid Salutation within TASS.web.  If empty string is provided, the person will be removed from the parent in TASS.

	`p2_initials [string]` - Parent 2 Initials.  If empty string is provided, the person will be removed from the parent in TASS.

	`p2_other_name [string]` - Parent 2 Other Name.  If empty string is provided, the person will be removed from the parent in TASS.

	`p2_suffix [string]` - Parent 2 Suffix.  If empty string is provided, the person will be removed from the parent in TASS.
	
	`ud1_flg to ud10_flg [string]` - Parent user defined flag

    `ud21_text to ud25_text [string]` - Parent user defined text
	



* **Success Response:**

	```javascript
	{
		"success": "You successfully saved 2 parent(s).",
		"__tassversion": "01.053.0.999",
		"token": {
			"data": [
			{
				"p2_first_name": "Karen",
				"surname": "Jones",
				"p1_other_name": "Daryl",
				"p2_surname": "Jones",
				"p2_other_name": "Alice",
				"p1_surname": "JonesX",
				"p2_initials": "K",
				"p1_occupation": "Nurse",
				"p1_preferred_name": "Jimmy",
				"id": 129225,
				"p2_title": "Miss",
				"p2_suffix": "BMMST",
				"p1_suffix": "Suff",
				"p1_initials": "J",
				"p1_title": "Mr",
				"p2_preferred_name": "Kazz",
				"p2_gender": "F",
				"p1_gender": "M",
				"p2_occupation": "Dentist",
				"p1_first_name": "Jimmy"
			},
				{
				"surname": "Smith",
				"p1_other_name": "",
				"p1_surname": "Smith",
				"p1_occupation": "Accountant",
				"p1_preferred_name": "Aaron",
				"id": 129226,
				"p1_suffix": "",
				"p1_initials": "A",
				"p1_title": "Mr",
				"p1_gender": "M",
				"p2_occupation": "",
				"p1_first_name": "Aaron"
				"p2_first_name": "",
				"p2_surname": "",
				"p2_other_name": "",
				"p2_initials": "",
				"p2_title": "",
				"p2_suffix": "",
				"p2_preferred_name": "",
				"p2_gender": "",
				"p2_occupation": "",
				}
			],
			"timestamp": "{ts '2020-08-06 07:11:30'}"
		}
	}
	```
 
* **Error Response:**

	`data` not supplied
	```javascript
	__invalid: {
		"data": "'data' is required."
	}
	```

	`[field_name]` is not valid
	```javascript
	__invalid: {
		"[field_name]": "'[field_name]' is not a valid field name"
	}
	```

	`[field_name]` is not supplied
	```javascript
	__invalid: {
		"[field_name]": "field is required"
	}
	```

	`id` not supplied
	```javascript
	__invalid: {
		"id": "Id is required for all rows."
	}
	```

	`id` is a duplicate parent code
	```javascript
	__invalid: {
		"id": "[id] is a duplicate parent code."
	}
	```

	`surname` not supplied
	```javascript
	__invalid: {
		"surname": "'surname' is required for all rows"
	}
	```

	`p1_surname` not supplied when other 'p1_' prefixed fields are present
	```javascript
	__invalid: {
		"surname": "'p1_surname' is required"
	}
	```

	`p1_first_name` not supplied when other 'p1_' prefixed fields are present
	```javascript
	__invalid: {
		"p1_first_name": "'p1_first_name' is required"
	}
	```

	`p1_preferred_name` not supplied when other 'p1_' prefixed fields are present
	```javascript
	__invalid: {
		"p1_preferred_name": "'p1_preferred_name' is required"
	}
	```

	`p1_gender` not supplied when other 'p1_' prefixed fields are present
	```javascript
	__invalid: {
		"gender": "'p1_gender' is required"
	}
	```

	`p1_gender` is not valid
	```javascript
	__invalid: {
		"gender": "'[p1_gender]' is not a valid gender"
	}
	```

	`p1_occupation` is not valid
	```javascript
	__invalid: {
		"occupation": "'[p1_occupation]' is not a valid occupation"
	}
	```

	`p1_title` is not valid
	```javascript
	__invalid: {
		"title": "'[p1_title]' is not a valid title"
	}
	```

	`p2_surname` not supplied when other 'p2_' prefixed fields are present
	```javascript
	__invalid: {
		"p2_surname": "'p2_surname' is required"
	}
	```

	`p2_first_name` not supplied when other 'p2_' prefixed fields are present
	```javascript
	__invalid: {
		"p2_first_name": "'p2_first_name' is required"
	}
	```

	`p2_preferred_name` not supplied when other 'p2_' prefixed fields are present
	```javascript
	__invalid: {
		"p2_preferred_name": "'p2_preferred_name' is required"
	}
	```

	`p2_gender` is not valid
	```javascript
	__invalid: {
		"gender": "'[p2_gender]' is not a valid gender"
	}
	```

	`p2_occupation` is not valid
	```javascript
	__invalid: {
		"occupation": "'[p2_occupation]' is not a valid occupation"
	}
	```

	`p2_title` is not valid
	```javascript
	__invalid: {
		"title": "'[p2_title]' is not a valid title"
	}
	```

		`id` is more than 8 characters
	```javascript
	__invalid: {
		"id": "exceeds 8 characters"
	}
	```

	`surname` is more than 30 characters
	```javascript
	__invalid: {
		"surname": "exceeds 30 characters"
	}
	```

	`p1_occupation` is more than 30 characters
	```javascript
	__invalid: {
		"p1_occupation": "exceeds 30 characters"
	}
	```

	`p1_title` is more than 15 characters
	```javascript
	__invalid: {
		"p1_title": "exceeds 15 characters"
	}
	```

	`p1_initials` is more than 5 characters
	```javascript
	__invalid: {
		"p1_initials": "exceeds 5 characters"
	}
	```

	`p1_surname` is more than 50 characters
	```javascript
	__invalid: {
		"p1_surname": "exceeds 50 characters"
	}
	```

	`p1_first_name` is more than 50 characters
	```javascript
	__invalid: {
		"p1_first_name": "exceeds 50 characters"
	}
	```

	`p1_other_name` is more than 50 characters
	```javascript
	__invalid: {
		"p1_other_name": "exceeds 50 characters"
	}
	```

	`p1_preferred_name` is more than 50 characters
	```javascript
	__invalid: {
		"p1_preferred_name": "exceeds 50 characters"
	}
	```

	`p1_suffix` is more than 30 characters
	```javascript
	__invalid: {
		"p1_suffix": "exceeds 30 characters"
	}
	```

	`p1_gender` is more than 50 characters
	```javascript
	__invalid: {
		"p1_gender": "exceeds 50 characters"
	}
	```

	`p2_occupation` is more than 30 characters
	```javascript
	__invalid: {
		"p2_occupation": "exceeds 30 characters"
	}
	```

	`p2_title` is more than 15 characters
	```javascript
	__invalid: {
		"p2_title": "exceeds 15 characters"
	}
	```

	`p2_initials` is more than 5 characters
	```javascript
	__invalid: {
		"p2_initials": "exceeds 5 characters"
	}
	```

	`p2_surname` is more than 50 characters
	```javascript
	__invalid: {
		"p2_surname": "exceeds 50 characters"
	}
	```

	`p2_first_name` is more than 50 characters
	```javascript
	__invalid: {
		"p2_first_name": "exceeds 50 characters"
	}
	```

	`p2_other_name` is more than 50 characters
	```javascript
	__invalid: {
		"p2_other_name": "exceeds 50 characters"
	}
	```

	`p2_preferred_name` is more than 50 characters
	```javascript
	__invalid: {
		"p2_preferred_name": "exceeds 50 characters"
	}
	```

	`p2_suffix` is more than 30 characters
	```javascript
	__invalid: {
		"p2_suffix": "exceeds 30 characters"
	}
	```

	`p2_gender` is more than 50 characters
	```javascript
	__invalid: {
		"p2_gender": "exceeds 50 characters"
	}
	```

	`ud1_flg to ud10_flg` is more than 1 character
	```javascript
	__invalid: {
		"[field]": "exceeds 1 character"
	}
	```

	`ud21_text to ud25_text` is more than 20 characters
	```javascript
	__invalid: {
		"[field]": "exceeds 20 characters"
	}
	```


* **Sample Parameters:**

	```javascript
	{
		"data":
			[
				{
					"id" : "129225"
					, "surname" : "Jones"
					, "p1_occupation" : "Builder"
					, "p1_title" : "Mr"
					, "p1_initials" : "J"
					, "p1_surname" : "Jones"
					, "p1_first_name" : "Jimmy"
					, "p1_other_name" : "Daryl"
					, "p1_preferred_name" : "Jimmy"
					, "p1_suffix" : "Suff"
					, "p1_gender" : "M"
					, "p2_occupation" : "Dentist"
					, "p2_title" : "Miss"
					, "p2_initials" : "K"
					, "p2_surname" : "Jones"
					, "p2_first_name" : "Karen"
					, "p2_other_name" : "Alice"
					, "p2_preferred_name" : "Kazz"
					, "p2_suffix" : "BMMST"
					, "p2_gender" : "F"
				}
				, {
					"id" : "129226"
					, "surname" : "Smith"
					, "p1_occupation" : "Accountant"
					, "p1_title" : "Mr"
					, "p1_initials" : "A"
					, "p1_surname" : "Smith"
					, "p1_first_name" : "Aaron"
					, "p1_other_name" : ""
					, "p1_preferred_name" : "Aaron"
					, "p1_suffix" : ""
					, "p1_gender" : "M"
					, "p2_occupation" : ""
					, "p2_title" : ""
					, "p2_initials" : ""
					, "p2_surname" : ""
					, "p2_first_name" : ""
					, "p2_other_name" : ""
					, "p2_preferred_name" : ""
					, "p2_suffix" : ""
					, "p2_gender" : ""
				}
			]
		}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?method=setParents&appcode=API21&company=10&v=2&token=BJVvYXC0We4Dtvp6Q49RqhBeAi6uqpTQ9t%2FKI9ZAFpCMeVXIFlDU5yNQIeYME%2BYLXgYA69RTUjXjLeVBetN6CaFMdPCKMWBXD%2Bkkt0%2Fuht0suYrSDONP6mx%2Fbt4WGgNOD5YoIYRNiIVDw2Qn2Oi5YodaEUgtGJohUJMzy3tqsX%2BraZk3j7d77okDCjb7MeFJ0DcupqUoRiGjE39415HTfPgNc6R6BY9wt7SJsj4yOPBrIxHQVS8Yy6gZ3nZgsJ5rhcdkB6eCI6b3FJ31s6vsVcbVu5NBY8AF1qqjWLMazduISzEBwRDsofXfJjo1KLX59R410bmbrF5Z7QZfEfE%2FlettTWOyb4EgdhBoC3v0aLOfF6Bt12AFXDo2VGbgryceeOLAscp%2FFr9ttH42hClBtWsxFU1N5dDENUsVHOwWcfCxd7aTtc0xjvaEYJWcZrRRZa1yrIvgeWaDk0LVxM5ePcT%2BltdrymgmxmZYgxdiYC1qQDcNXDx9hN7yKeZDUztwGA0yl2iXW8aBXAy5hRnztR0TrREyOba26mUHxUJO7tfpIyOrpPbE0nR18vtCZ%2BinbvyqN9adpZhQPByG2XD9M6MoYdmBCc3Duv9qb%2BIa0A8%3D
	```
	
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		 <input type="hidden" name="method" value="setParents">
		 <input type="hidden" name="appcode" value="API21">
		 <input type="hidden" name="company" value="10">
		 <input type="hidden" name="v" value="2">
		 <textarea name="token">BJVvYXC0We4Dtvp6Q49RqhBeAi6uqpTQ9t/KI9ZAFpCMeVXIFlDU5yNQIeYME+YLXgYA69RTUjXjLeVBetN6CaFMdPCKMWBXD+kkt0/uht0suYrSDONP6mx/bt4WGgNOD5YoIYRNiIVDw2Qn2Oi5YodaEUgtGJohUJMzy3tqsX+raZk3j7d77okDCjb7MeFJ0DcupqUoRiGjE39415HTfPgNc6R6BY9wt7SJsj4yOPBrIxHQVS8Yy6gZ3nZgsJ5rhcdkB6eCI6b3FJ31s6vsVcbVu5NBY8AF1qqjWLMazduISzEBwRDsofXfJjo1KLX59R410bmbrF5Z7QZfEfE/lettTWOyb4EgdhBoC3v0aLOfF6Bt12AFXDo2VGbgryceeOLAscp/Fr9ttH42hClBtWsxFU1N5dDENUsVHOwWcfCxd7aTtc0xjvaEYJWcZrRRZa1yrIvgeWaDk0LVxM5ePcT+ltdrymgmxmZYgxdiYC1qQDcNXDx9hN7yKeZDUztwGA0yl2iXW8aBXAy5hRnztR0TrREyOba26mUHxUJO7tfpIyOrpPbE0nR18vtCZ+inbvyqN9adpZhQPByG2XD9M6MoYdmBCc3Duv9qb+Ia0A8=</textarea>
	</form>
	```
