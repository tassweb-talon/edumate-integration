**SetParentAddress**
----
	Returns "success" and a count of updated parent address(es), or a structure of invalid validations "__invalid" belonging to parent address(es).

* **Version History:**

    TASS v53.2.nnn - Method Added.

* **Version:**

	2
    
* **Method:**

	`GET | POST`
	
*  **Params:**

	**Required:**
 
 	`data [array]` - Main data array containing parents and their addresses.

	`parentcode [string]` - Parent Code.

	`addresses [array]` - Array of addresses.

		2 items are required in each address array item

		`id [string]` - the type of address (e.g. home, work, postal)

		`parent_name [string]` - the parent name for the address

	**Optional:**

	`addresses [array]` contains the following optional fields.

		`addrline1 [string]` - Address line 1.
		
		`addrline2 [string]` - Address line 2.
		
		`addrline3 [string]` - Address line 3.
		
		`town_suburb [string]` - Town or Suburb.
		
		`state_code [string]` - State.
		
		`post_code [string]` - Post Code.
		
		`country [string]` - Country.
		
		`home_phone [string]` - Home phone number.
		
		`business_phone [string]` - Business phone number.
		
		`fax [string]` - Fax number.
		
		`salutation [string]` - Salutation for address.
		
		`e_mail1 [string]` - Email 1.
		
		`mobile1 [string]` - Mobile phone 1.
		
		`sms_flg1 [string]` - SMS flag for Mobile phone 1 (to allow SMS communication).
		
		`e_mail2 [string]` - Email 2.
		
		`mobile2 [string]` - Mobile phone 2.
		
		`sms_flg2 [string]` - SMS flag for Mobile phone 2 (to allow SMS communication).
	


* **Success Response:**

	```javascript
	{
		"success": "You successfully saved 2 parent address(es).",
		"__tassversion": "01.052.0.999",
		"token": {
			"data": [
				{
				"addresses": [
						{
							"town_suburb": "Mount Louisa",
							"mobile2": "0422665885",
							"e_mail1": "fbloggs@somewhere.com",
							"e_mail2": "anotherbloggs@somewhere.com",
							"sms_flg2": "N",
							"sms_flg1": "Y",
							"state_code": "QLD",
							"business_phone": "0752369854",
							"country": "Australia",
							"salutation": "Mr Bloggs",
							"parent_name": "Fred Bloggs",
							"addrline3": "",
							"addrline1": "Unit 1",
							"post_code": 4817,
							"home_phone": "0745852358",
							"id": "home",
							"addrline2": "123 Here Street",
							"fax": "",
							"mobile1": "0438996558"
						},
						{
							"town_suburb": "Hendra",
							"mobile2": "",
							"e_mail1": "kbloggs@blogger.com",
							"e_mail2": "",
							"sms_flg2": "",
							"sms_flg1": "Y",
							"state_code": "QLD",
							"business_phone": "",
							"country": "Australia",
							"salutation": "Ms Bloggs",
							"parent_name": "Kerry Bloggs",
							"addrline3": "",
							"addrline1": "9 Turtle Street",
							"post_code": 4005,
							"home_phone": "",
							"id": "postal",
							"addrline2": "",
							"fax": "",
							"mobile1": "0411458985"
						}
					],
					"parentcode": 129225
				}
			],
			"timestamp": "{ts '2020-08-19 21:00:45'}"
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

	`id` not supplied
	```javascript
	__invalid: {
		"id": "Id is required for all rows."
	}
	```

	`parent_name` not supplied
	```javascript
	__invalid: {
		"parent_name": "'parent_name' is required for all rows"
	}
	```

	`addrline1` is more than 60 characters
	```javascript
	__invalid: {
		"addrline1": "exceeds 60 characters"
	}
	```

	`addrline2` is more than 60 characters
	```javascript
	__invalid: {
		"addrline2": "exceeds 60 characters"
	}
	```

	`addrline3` is more than 60 characters
	```javascript
	__invalid: {
		"addrline3": "exceeds 60 characters"
	}
	```

	`town_suburb` is more than 50 characters
	```javascript
	__invalid: {
		"town_suburb": "exceeds 50 characters"
	}
	```

	`state_code` is more than 3 characters
	```javascript
	__invalid: {
		"state_code": "exceeds 3 characters"
	}
	```

	`post_code` is more than 12 characters
	```javascript
	__invalid: {
		"post_code": "exceeds 12 characters"
	}
	```

	`country` is more than 40 characters
	```javascript
	__invalid: {
		"country": "exceeds 40 characters"
	}
	```

	`home_phone` is more than 30 characters
	```javascript
	__invalid: {
		"home_phone": "exceeds 30 characters"
	}
	```

	`business_phone` is more than 30 characters
	```javascript
	__invalid: {
		"business_phone": "exceeds 30 characters"
	}
	```

	`fax` is more than 30 characters
	```javascript
	__invalid: {
		"fax": "exceeds 30 characters"
	}
	```

	`salutation` is more than 60 characters
	```javascript
	__invalid: {
		"salutation": "exceeds 60 characters"
	}
	```

	`e_mail1` is more than 140 characters
	```javascript
	__invalid: {
		"e_mail1": "exceeds 140 characters"
	}
	```

	`mobile1` is more than 30 characters
	```javascript
	__invalid: {
		"mobile1": "exceeds 30 characters"
	}
	```

	`sms_flg1` is more than 1 characters
	```javascript
	__invalid: {
		"sms_flg1": "exceeds 1 characters"
	}
	```

	`e_mail2` is more than 140 characters
	```javascript
	__invalid: {
		"e_mail2": "exceeds 140 characters"
	}
	```

	`mobile2` is more than 30 characters
	```javascript
	__invalid: {
		"mobile2": "exceeds 30 characters"
	}
	```

	`sms_flg2` is more than 1 characters
	```javascript
	__invalid: {
		"sms_flg2": "exceeds 1 characters"
	}
	```


* **Sample Parameters:**

	```javascript
	{
	    "data":
	    [
	        {
	            "parentcode" : "129225"
	            , "addresses" : [
	                {
	                    "id" : "home"
	                    , "parent_name" : "Fred Bloggs"
	                    , "addrline1" : "Unit 1"
	                    , "addrline2" : "123 Here Street"
	                    , "addrline3" : ""
	                    , "town_suburb" : "Mount Louisa"
	                    , "state_code" : "QLD"
	                    , "post_code" : "4817"
	                    , "country" : "Australia"
	                    , "home_phone" : "0745852358"
	                    , "business_phone" : "0752369854"
	                    , "fax" : ""
	                    , "salutation" : "Mr Bloggs"
	                    , "e_mail1" : "fbloggs@somewhere.com"
	                    , "e_mail2" : "anotherbloggs@somewhere.com"
	                    , "mobile1" : "0438996558"
	                    , "sms_flg1" : "Y"
	                    , "mobile2" : "0422665885"
	                    , "sms_flg2" : "N"
	                }
	                , {
	                    "id" : "postal"
	                    , "parent_name" : "Kerry Bloggs"
	                    , "addrline1" : "9 Turtle Street"
	                    , "addrline2" : ""
	                    , "addrline3" : ""
	                    , "town_suburb" : "Hendra"
	                    , "state_code" : "QLD"
	                    , "post_code" : "4005"
	                    , "country" : "Australia"
	                    , "home_phone" : ""
	                    , "business_phone" : ""
	                    , "fax" : ""
	                    , "salutation" : "Ms Bloggs"
	                    , "e_mail1" : "kbloggs@blogger.com"
	                    , "e_mail2" : ""
	                    , "mobile1" : "0411458985"
	                    , "sms_flg1" : "Y"
	                    , "mobile2" : ""
	                    , "sms_flg2" : ""
	                }
	            ]
	        }
	    ]
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?method=setParentAddress&appcode=API21&company=10&v=2&token=BJVvYXC0We4Dtvp6Q49RqhBeAi6uqpTQ9t%2FKI9ZAFpCMeVXIFlDU5yNQIeYME%2BYLXgYA69RTUjXjLeVBetN6CaFMdPCKMWBXD%2Bkkt0%2Fuht0suYrSDONP6mx%2Fbt4WGgNOD5YoIYRNiIVDw2Qn2Oi5YodaEUgtGJohUJMzy3tqsX%2BraZk3j7d77okDCjb7MeFJ0DcupqUoRiGjE39415HTfPgNc6R6BY9wt7SJsj4yOPBrIxHQVS8Yy6gZ3nZgsJ5rhcdkB6eCI6b3FJ31s6vsVcbVu5NBY8AF1qqjWLMazduISzEBwRDsofXfJjo1KLX59R410bmbrF5Z7QZfEfE%2FlettTWOyb4EgdhBoC3v0aLOfF6Bt12AFXDo2VGbgryceeOLAscp%2FFr9ttH42hClBtWsxFU1N5dDENUsVHOwWcfCxd7aTtc0xjvaEYJWcZrRRZa1yrIvgeWaDk0LVxM5ePcT%2BltdrymgmxmZYgxdiYC1qQDcNXDx9hN7yKeZDUztwGA0yl2iXW8aBXAy5hRnztR0TrREyOba26mUHxUJO7tfpIyOrpPbE0nR18vtCZ%2BinbvyqN9adpZhQPByG2XD9M6MoYdmBCc3Duv9qb%2BIa0A8%3D
	```
	
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		 <input type="hidden" name="method" value="setParentAddress">
		 <input type="hidden" name="appcode" value="API21">
		 <input type="hidden" name="company" value="10">
		 <input type="hidden" name="v" value="2">
		 <textarea name="token">BJVvYXC0We4Dtvp6Q49RqhBeAi6uqpTQ9t/KI9ZAFpCMeVXIFlDU5yNQIeYME+YLXgYA69RTUjXjLeVBetN6CaFMdPCKMWBXD+kkt0/uht0suYrSDONP6mx/bt4WGgNOD5YoIYRNiIVDw2Qn2Oi5YodaEUgtGJohUJMzy3tqsX+raZk3j7d77okDCjb7MeFJ0DcupqUoRiGjE39415HTfPgNc6R6BY9wt7SJsj4yOPBrIxHQVS8Yy6gZ3nZgsJ5rhcdkB6eCI6b3FJ31s6vsVcbVu5NBY8AF1qqjWLMazduISzEBwRDsofXfJjo1KLX59R410bmbrF5Z7QZfEfE/lettTWOyb4EgdhBoC3v0aLOfF6Bt12AFXDo2VGbgryceeOLAscp/Fr9ttH42hClBtWsxFU1N5dDENUsVHOwWcfCxd7aTtc0xjvaEYJWcZrRRZa1yrIvgeWaDk0LVxM5ePcT+ltdrymgmxmZYgxdiYC1qQDcNXDx9hN7yKeZDUztwGA0yl2iXW8aBXAy5hRnztR0TrREyOba26mUHxUJO7tfpIyOrpPbE0nR18vtCZ+inbvyqN9adpZhQPByG2XD9M6MoYdmBCc3Duv9qb+Ia0A8=</textarea>
	</form>
	```