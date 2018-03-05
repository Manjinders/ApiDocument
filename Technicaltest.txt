**Start Test Api**
----
Description : get the test  for user.

* **URL**

  api/TechnicalTestApi/StartTest/{examdetailId}

* **Method:** 

    Get

* **Method:** 
    
	Header
	Authorization: bearer your jwt token

* **Success Response:**

	Code: 200 
	

* **Error Response:**

	Code: 403 Invalid credentials



** Submitt the test response  Api**
----
Description :Submitt the test response.

* **URL**

    api/TechnicalTestApi/SubmitTest

* **Method:** 

    POST
    Header
	
	Authorization: bearer your jwt token

* **Data Params** <br />

<pre>
{
	Testdata   {String} 
	Filebase64  {base64string} 
	examdetailId {int}     
}	 
</pre>   

* **Example:** <br/>

<pre>
{
	Testdata   "you code"
	Filebase64  file in base 64 format
	examdetailId 124 

}
</pre>  
* **Success Response:**

	Code: 200 

* **Error Response:**

	Code: 400 NOT FOUND

