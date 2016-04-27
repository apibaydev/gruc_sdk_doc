# Users

###Subaccounts
#####GET
#####Resource URI
/v1/accounts/{account_sid}
#####Description
This action allows API consumer to get sub-account information. 
#####Parameter
<table>
<tbody>
<tr><td><b>Parameter</td><td><b>ML</td><td><b>R</td><td><b>Default</td><td><b>Description</td><td><b>Data Type</b></td></tr>
<tr><td>account_sid</td><td>34</td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the sub-account</td><td>String</td></tr>
<tr><td>developer_id</td><td> </td><td>O</td><td> </td><td>The API consumer CaaS is a special one. It has multiple developers who assigned different API keys. <Br/>This parameter is only for platform internal use.</td><td>String</td></tr>
</tbody>
</table>


#####Response
* JSON

		{
			“sid”: “AC5di30gkr4jd83k29dir93pr003gte8lj4d”,
			“login_id”: “YourNickname”
			“status”: “active”,
			“balance”: “S$10.0”,
			“first_name”: “YourFirstName”,
			“last_name”: “YourLastName”,
			“email”: “YourEmailAddress”,
			“phone_number”: “YourPhoneNumber”,
			“date_created”: “15 Dec 2014 14:20:25 +0000”,
			“date_updated”: “15 Dec 2014 14:20:25 +0000”
		}

* XML

To be filled

#####Sample


####POST

#####Resource URI

/v1/accounts

#####Description
This action allows API consumer to create a sub-account. As default, the sub-account would be prepaid. And at the same time, we will create a default SIP account and a SIP account alias for the sub-account.


#####Parameter
<table>
<tbody>
<tr><td><b>Parameter</td><td><b>ML</td><td><b>R</td><td><b>Default</td><td><b>Description</td><td><b>Data Type</b></td></tr>
<tr><td>login_id</td><td> </td><td>R</td><td> </td><td>Register ID</td><td>String</td></tr>
<tr><td>password</td><td> </td><td>R</td><td> </td><td>Password</td><td>String</td></tr>
<tr><td>encrypt_type</td><td> </td><td>O</td><td>0</td><td>0 - plain text<Br/>
1 – encrypted password via AES</td><td> </td></tr>
<tr><td>first_name</td><td> </td><td>O</td><td> </td><td>first name</td><td>String</td></tr>
<tr><td>last_name</td><td> </td><td>O</td><td> </td><td>last name</td><td>String</td></tr>
<tr><td>email</td><td> </td><td>O</td><td> </td><td>email</td><td>String</td></tr>
<tr><td>mobile_phone</td><td> </td><td>O</td><td> </td><td>Mobile phone number</td><td>String</td></tr>
<tr><td>domain</td><td> </td><td>O</td><td> </td><td>SIP domain name, if not put, will use the default</td><td>String</td></tr>
</tbody>
</table>

####Response
* JSON
* 
		{
			“sid”: ”AC5di30gkr4jd83k29dir93pr003gte8lj4d”,
			“login_id”: “YourNickname”
			“date_created”: “2014-12-15 12:20:25 +0000”,
			“status”: “active”,
			“domain”: “sip.caas.com”,
			“sub_resource_uris”: {
				“sip_accounts”: “/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/SIP.json”,
				“sip_aliases”: “/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/SIP/ 
		SC3ei3pv3r4j0v3kd2cirtd39c4wgte8lp7y/aliases.json”,
				“balance_adjustment”:“/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/balance_adjustment.json”,
				“IP2IP_reminder_max_time”: 
		“/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/calls/IP2IP/reminder_max_time.json”,
				“IP2P_reminder_max_time”:
		“/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/calls/IP2P/reminder_max_time.json”,
				“cdrs”: “/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/cdrs.json”
			}
			"uri": "/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d.json"
		}

* XML

	To be filled
#####Sample
####PUT
#####Resource URI
/v1/accounts/{account_sid}
#####Description
This action allows API consumer to update a sub-account.

#####Parameter

<table>
<tbody>
<tr><td><b>Parameter</td><td><b>ML</td><td><b>R</td><td><b>Default</td><td><b>Description</td><td><b>Data Type</b></td></tr>
<tr><td>account_sid</td><td>34</td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the sub-account</td><td>String</td></tr>
<tr><td>password</td><td> </td><td>O</td><td> </td><td>Password encrypted via AES</td><td>String</td></tr>
<tr><td>first_name</td><td> </td><td>O</td><td> </td><td>first name</td><td>String</td></tr>
<tr><td>last_name</td><td> </td><td>O</td><td> </td><td>last name</td><td>String</td></tr>
<tr><td>email</td><td> </td><td>O</td><td> </td><td>email</td><td>String</td></tr>
<tr><td>mobile_phone</td><td> </td><td>O</td><td> </td><td>Mobile phone number</td><td>String</td></tr>
<tr><td>status</td><td> </td><td>O</td><td> </td><td>Account status</td><td> </td></tr>
<tr><td>domain</td><td> </td><td>O</td><td> </td><td>SIP domain name, if not put, will use the default</td><td>String</td></tr>
</tbody>
</table>
####Response
* JSON
			
		{
			“sid”: ”AC5di30gkr4jd83k29dir93pr003gte8lj4d”,
			“login_id”: “YourNickname”
			“date_updated”: “2014-12-15 12:20:25 +0000”,
			“status”: “active”,
			“domain”: “sip.caas.com”,
			“sub_resource_uris”: {
				“sip_accounts”: “/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/SIP.json”,
				 “sip_aliases”: “/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/SIP/ 
		SC3ei3pv3r4j0v3kd2cirtd39c4wgte8lp7y/aliases.json”,
				“balance_adjustment”:“/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/balance_adjustment.json”,
				“IP2IP_reminder_max_time”: 
		“/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/calls/IP2IP/reminder_max_time.json”,
				“IP2P_reminder_max_time”: 
		“/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/calls/IP2P/reminder_max_time.json”,
				“IP2P_reminder_max_time”: 
		“/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/calls/P2IP/reminder_max_time.json”,
				 “cdrs”: “/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/cdrs.json”
			}
			"uri": "/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d.json"
		}

* XML

	To be filled
#####Sample
####SIP Accounts
#####GET

#####Resource URI
	/v1/accounts/{account_sid}/SIP/{sip_sid}
####Description
This action allows API consumer to get SIP account information for a sub-account. 
####Parameter
<table>
<tbody>
<tr><td><b><em>Parameter</td><td><b><em>ML</td><td><b><em>R</td><td><b><em>Default</td><td><b><em>Description</td><td><b><em>Data Type</b></td></tr>
<tr><td>sid</td><td>34</td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the SIP account</td><td>String</td></tr>
<tr><td>account_sid</td><td>34</td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the sub-account</td><td>String</td></tr>
</tbody>
</table>

####Response
* JSON

		{
			“sid”: “SCjti38m7r4j0v3kd2ciri76rb4wgte8lp0q”,
			“sip_id”: “DefaultSIPID”,
			“sip_aliases”: [“alias1”,”alias2”,”alias3”],
			“date_created”: “2014-12-15 12:20:25 +0000”,
			“status”: “active”,
			“domain”: “sip.caas.com”,
			“sub_resource_uris”: {
				“sip_aliases”: 
		“/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/SIP/SCjti38m7r4j0v3kd2ciri76rb4wgte8lp0q/aliases.json”
			}
		}

* XML

To be filled

####Sample
####POST
#####Resource URI
/v1/accounts/{account_sid}/SIP
#####Description
This action allows API consumer to create a SIP account for a sub-account.
#####Parameter
<table>
<tbody>
<tr><td><b><em>Parameter</td><td><b><em>ML</td><td><b><em>R</td><td><b><em>Default</td><td><b><em>Description</td><td><b><em>Data Type</b></td></tr>
<tr><td>account_sid</td><td>34</td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the sub-account</td><td>String</td></tr>
<tr><td>password</td><td> </td><td>R</td><td> </td><td>Encrypted password via AES</td><td>String</td></tr>
<tr><td>domain</td><td> </td><td>O</td><td> </td><td>If not put, will use the default SIP domain name</td><td>String</td></tr>
</tbody>
</table>

####Response
* JSON

		{
			“sid”: “SCjti38m7r4j0v3kd2ciri76rb4wgte8lp0q”,
			“sip_id”: “DefaultSIPID”,
			“sip_alias”: “DefaultSIPAlias”,
			“date_created”: “2014-12-15 12:20:25 +0000”,
			“status”: “active”,
			“sub_resource_uris”: {
				“sip_aliases”: 
		“/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/SIP/SCjti38m7r4j0v3kd2ciri76rb4wgte8lp0q/aliases.json”
			},
			"uri": "/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/SIP/SCjti38m7r4j0v3kd2ciri76rb4wgte8lp0q.json"
		}

* XML

To be filled
#####Sample
#####PUT
#####Resource URI
		/v1/accounts/{account_sid}/SIP/{sip_sid}
#####Description
This action allows API consumer to update a SIP account for a sub-account.
#####Parameter

<table>
<tbody>
<tr><td><b><em>Parameter</td><td><b><em>ML</td><td><b><em>R</td><td><b><em>Default</td><td><b><em>Description</td><td><b><em>Data Type</b></td></tr>
<tr><td>account_sid</td><td>34</td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the sub-account</td><td>String</td></tr>
<tr><td>sid</td><td> </td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the SIP account.</td><td> </td></tr>
<tr><td>password</td><td> </td><td>R</td><td> </td><td>Encrypted password via AES</td><td>String</td></tr>
<tr><td>domain</td><td> </td><td>R</td><td> </td><td>SIP domain name</td><td>String</td></tr>
</tbody>
</table>

#####Response
* JSON

		{
			“sid”: “SCjti38m7r4j0v3kd2ciri76rb4wgte8lp0q”,
			“sip_id”: “DefaultSIPID”,
			“sip_alias”: “DefaultSIPAlias”,
			“date_updated”: “15 Dec 2014 14:20:25 +0000”,
			“status”: “active”,
			“sub_resource_uris”: {
				 “sip_aliases”: 
		“/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/SIP/SCjti38m7r4j0v3kd2ciri76rb4wgte8lp0q/aliases.json”
			}
		}
* XML

	To be filled
#####Sample
#####DELETE
#####Resource URI
		/v1/accounts/{account_sid}/SIP/{sip_sid}

#####Description
This action allows API consumer to update a SIP account for a sub-account. 
####Parameter
<table>
<tbody>
<tr><td><b><em>Parameter</td><td><b><em>ML</td><td><b><em>R</td><td><b><em>Default</td><td><b><em>Description</td><td><b><em>Data Type</b></td></tr>
<tr><td>account_sid</td><td>34</td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the sub-account</td><td>String</td></tr>
<tr><td>sid</td><td> </td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the SIP account.</td><td> </td></tr>
</tbody>
</table>

#####Response
* JSON

* XML

	To be filled
#####Sample
#####SIP Accounts Aliases
#####GET
#####Resource URI
		/v1/accounts/{account_sid}/SIP/{sip_sid}/aliases
		/v1/accounts/{account_sid}/SIP/{sip_sid}/aliases/{alias_sid}

#####Description
This action allows API consumer to get SIP account alias (es). 
#####Parameter

<table>
<tbody>
<tr><td><b><em>Parameter</td><td><b><em>ML</td><td><b><em>R</td><td><b><em>Default</td><td><b><em>Description</td><td><b><em>Data Type</b></td></tr>
<tr><td>sid</td><td>34</td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the alias</td><td>String</td></tr>
<tr><td>account_sid</td><td>34</td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the sub-account</td><td> String</td></tr>
<tr><td>sip_sid</td><td>34</td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the SIP account</td><td>String</td></tr>
</tbody>
</table>

#####Response
* JSON

		{
			 “sid”: “SAfdi38m7r4j0v3kd2ciri76rb4wgte8lp4w”,
			“sip_alias”: “alias1”,
			“date_created”: “2014-12-15 12:20:25 +0000”,
			“date_updated”: “15 Dec 2014 14:20:25 +0000”,
			“status”: “active”,
			“domain”: “sip.caas.com”,
		}
* XML

	To be filled
#####Sample
#####POST
#####Resource URI
	/v1/accounts/{account_sid}/SIP/{sip_sid}/aliases
#####Description
This action allows API consumer to create an alias for a SIP account.
#####Parameter
<table>
<tbody>
<tr><td><b><em>Parameter</td><td><b><em>ML</td><td><b><em>R</td><td><b><em>Default</td><td><b><em>Description</td><td><b><em>Data Type</b></td></tr>
<tr><td>alias</td><td>34</td><td>R</td><td> </td><td>SIP ID alias. </td><td>String</td></tr>
<tr><td>account_sid</td><td>34</td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the sub-account</td><td> String</td></tr>
<tr><td>sip_sid</td><td>34</td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the SIP account</td><td> </td></tr>
</tbody>
</table>

#####Response
* JSON

		{
			“sid”: “SAfdi38m7r4j0v3kd2ciri76rb4wgte8lp4w”,
			“sip_alias”: “alias1”,
			“date_created”: “2014-12-15 12:20:25 +0000”,
			“status”: “active”,
			"uri": 
		"/v1/accounts/AC5di30gkr4jd83k29dir93pr003gte8lj4d/SIP/SCjti38m7r4j0v3kd2ciri76rb4wgte8lp0q/aliaes/SAfdi38m7r4j0v3kd2ciri76rb4wgte8lp4w.json"
		}

* XML

	To be filled
#####Sample
#####PUT
#####Resource URI
	/v1/accounts/{account_sid}/SIP/{sip_sid}/aliases/{alias_sid} 
#####Description
This action allows API consumer to update an alias for a SIP account. 
#####Parameter
<table>
<tbody>
<tr><td><b><em>Parameter</td><td><b><em>ML</td><td><b><em>R</td><td><b><em>Default</td><td><b><em>Description</td><td><b><em>Data Type</b></td></tr>
<tr><td>account_sid</td><td>34</td><td>R</td><td> </td><td>Sub-account ID of a developer. If passed, will return the subaccount's CDR; developer's CDR, otherwise. </td><td>String</td></tr>
<tr><td>sip_sid</td><td>34</td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the SIP account</td><td> </td></tr>
<tr><td>alias_sid</td><td> </td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the SIP alias.</td><td>String</td></tr>
<tr><td>alias</td><td> </td><td>R</td><td> </td><td>SIP ID alias. </td><td>String</td></tr>
</tbody>
</table>

#####Response
* JSON

		{
			“sid”: “SAfdi38m7r4j0RESPONSE
			3kd2ciri76rb4wgte8lp4w”,
			“sip_alias”: “alias1”,
			“date_updated”: “2014-12-15 12:20:25 +0000”,
			“status”: “active”
		}
* XML

    To be filled

**Sample**

**DELETE**

**Resource URI**
/v1/accounts/{account_sid}/SIP/{sip_sid}/aliases/{alias_sid}

**Description**

This action allows API consumer to update an alias for a SIP account.

**Parameter**

<table>
<tbody>
<tr><td><b><em>Parameter</td><td><b><em>ML</td><td><b><em>R</td><td><b><em>Default</td><td><b><em>Description</td><td><b><em>Data Type</b></td></tr>
<tr><td>account_sid</td><td>34</td><td>R</td><td> </td><td>Sub-account ID of a developer. If passed, will return the subaccount's CDR; developer's CDR, otherwise. </td><td>String</td></tr>
<tr><td>sip_sid</td><td>34</td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the SIP account</td><td>  </td></tr>
<tr><td>alias_sid</td><td> </td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the SIP alias.</td><td>String</td></tr>
</tbody>
</table>

**Response**

* JSON

* XML

	To be filled

**Sample**

**Balances**

**GET**

**Resource URI**

	/v1/accounts/{account_id}/balances
**Description**

This service allows API consumer to get the balance for a sub-account. 

**Inputs**

<table>
<tbody>
<tr><td><b><em>Parameter</td><td><b><em>ML</td><td><b><em>R</td><td><b><em>Default</td><td><b><em>Description</td><td><b><em>Data Type</b></td></tr>
<tr><td>account_sid</td><td> </td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the sub-account</td><td>String</td></tr>
</tbody>
</table>

**Response**

* JSON

		{
			“balance”: “S$100”
		}

* XML

	To be filled

* Sample

	-

**POST**

**Resource URI**

	/v1/accounts/{account_id}/balances

**Description**

This service allows API consumer to top up or adjust the balance for a sub-account. 

**Inputs**

<table>
<tbody>
<tr><td><b><em>Parameter</td><td><b><em>ML</td><td><b><em>R</td><td><b><em>Default</td><td><b><em>Description</td><td><b><em>Data Type</b></td></tr>
<tr><td>account_sid</td><td> </td><td>R</td><td> </td><td>A 34 character string that uniquely identifies the sub-account</td><td>String</td></tr>
<tr><td>amount</td><td> </td><td>R</td><td> </td><td>Adjustment amount</td><td>Number  </td></tr>
<tr><td>type</td><td> </td><td>R</td><td> </td><td>Adjustment type. </Br>The values-</Br>
TOPUP</Br>
ADJUSTMENT</td><td>String</td></tr>
<tr><td>pay_method</td><td> </td><td>R</td><td> </td><td>The values-<Br>
1- pay balance<Br>
2- YeePay<Br>
3- cash on arrival<Br>
4- paypal<Br>
5- alipay<Br>
6- buy service<Br>
7- system is presented<Br>
8- unicompay<Br>
9- brpay<Br>
10- topup<Br>
242-purchase </td><td> </td></tr>
<tr><td>refer_trans_id</td><td> </td><td>O</td><td> </td><td>Third party reference transaction ID</td><td>String</td></tr>
<tr><td>desc</td><td> </td><td>O</td><td> </td><td>description</td><td>String</td></tr>
</tbody>
</table>
**Response**

* JSON


		{
			“sid”: “BAu62gtm7r4j0v3kd2ciri76rb4wgte8ld2q”,
			“balance”: “S$100”,
			“date_updated”: “15 Dec 2014 14:20:25 +0000”,
		}

* XML

	To be filled

**Sample**

-
