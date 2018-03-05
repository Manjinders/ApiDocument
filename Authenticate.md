**Facebook Authenticate Api**
----
Description : authenticate the user.

* **URL**

   api/AccountApi/Login/callbackUrl

* **Method:** 

    Get

* **Success Response:**

	Code: 200 
	
* **Content:**<br />
 
<pre>
https://graph.facebook.com/oauth/authorize?client_id=236311273578424&redirect_uri=callbackUrl&scope=email, publish_actions, public_profile"

</pre>

**Facebook code authenticate Api**
----
Description :Facebook callback url send authentication code.

* **URL**

    api/AccountApi/Facebook

* **Method:** 

    POST
  

* **Data Params** <br />

<pre>
{
	code   {String}
	
}	 
</pre>   

* **Example:** <br/>

<pre>
{	"code":"AQAtkL5KBZnpQvIb_oLRy_BnoFe27VPKA3T0jjpJAvwBKCrGPyKHlcJp-4QIwKrIDX55veQfEQXLea15FFfXnQwLUvybt9ixvsCETmHG2ZX6P8dg2PIxpS7YXcNtmRx0_aJa3rglsDITYGLbUdLuXWxTDSgNT-w_P9gSGrNrDzjoyfLh4JvN2oMi7",
	
}
</pre>  

* **Success Response:**

	Code: 200 
	
* **Content:**<br />
 
<pre>
{
    "First_Name": "Test",
    "Last_Name": "Test",
    "Gender": "male",
    "Locale": "en_US",
    "Link": "https://www.facebook.com/app_scoped_use",
    "Id": 1500323313409825,
    "Email": "test@gmail.com",
    "Roles": null,
    "JwtToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1bmlxdWVfbmFtZSI6Im1hbmppbmRlci5pbXBp"
}
</pre>
	
* **Error Response:**

	Code: 400 NOT FOUND

* **Content:**<br />
	
<pre>
{
    "Message": "{\"error\":{\"message\":\"This authorization code has been used.\",\"type\":\"OAuthException\",\"code\":100,\"fbtrace_id\":\"HpWMVBuIU4p\"}}"
}
</pre>

OR

<pre>
{
    "Message": "Error occurred. Please try again."
}
</pre>