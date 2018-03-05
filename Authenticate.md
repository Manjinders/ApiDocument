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

** Facebook code authenticate Api**
----
Description :Facebook callback url send authentication code.

* **URL**

    api/AccountApi/Facebook

* **Method:** 

    POST
  

* **Data Params** <br />

<pre>
{
	code   {String} *Required User's email address.
	
}	 
</pre>   

* **Example:** <br/>

<pre>
{	"code":"AQAtkL5KBZnpQvIb_oLRy_BnoFe27VPKA3T0jjpJAvwBKCrGPyKHlcJp-4QIwKrIDX55veQfEQXLea15FFfXnQwLUvybt9ixvsCETmHG2ZX6P8dg2PIxpS7YXcNtmRx0_aJa3rglsDITYGLbUdLuXWxTDSgNT-w_P9gSGrNrDzjoyfLh4JvN2oMi7_Ka48iD4qDoQfvXqmJKVhh3hPQoCF_pPKPUKvcWt2E7TdfTTKTfsSi3033mRFY09nlgpR_-nJIFIdGeOD3-RcUZsdG7WEKlo56tCgHMrN3KxE3b2yJHapG63o0fhA5aiolDJ7CYIqc2yFpK0DnVUHJEuziljuJh",
	
}
</pre>  

* **Success Response:**

	Code: 200 
	
* **Content:**<br />
 
<pre>
{
    "First_Name": "Manjinder",
    "Last_Name": "Singh",
    "Gender": "male",
    "Locale": "en_US",
    "Link": "https://www.facebook.com/app_scoped_user_id/1500323313409825/",
    "Id": 1500323313409825,
    "Email": "manjinder.impinge@gmail.com",
    "Roles": null,
    "JwtToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1bmlxdWVfbmFtZSI6Im1hbmppbmRlci5pbXBpbmdlQGdtYWlsLmNvbSIsIm5iZiI6MTUyMDI0NzI5NSwiZXhwIjoxNTIwMjQ5MDk0LCJpYXQiOjE1MjAyNDcyOTV9.QCb78MqJHsLYrY7avXNU_Tkn7igbwEAWdhsbSK-i0r4"
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