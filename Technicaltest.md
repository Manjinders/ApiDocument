**Start Test Api**
----
Description : get the test  for user.

* **URL**

  api/TechnicalTestApi/StartTest/{examdetailId}

* **Method:** 

    Get

* **Header:** 
    	
	ContentType: application/json

* **Success Response:**

	Code: 200 
	

* **Error Response:**

	Code: 403 Invalid credentials



**Submitt the test response  Api**
----
Description :Submitt the test response.

* **URL**

    api/TechnicalTestApi/SubmitTest

* **Method:** 

    PUT
* **Header:** 
    	
	ContentType: application/json

* **Data Params** <br />

<pre>
{
	Testdata   {String}
	FileName	{String}
	Filebase64  {base64string} 
	
	examdetailId {int}     
}	 
</pre>   

* **Example:** <br/>

<pre>
{
	Testdata   "your code"
	FileName	"abc.rar"  Full file name with extension "Rquired"
	Filebase64  file in base 64 format
	examdetailId 124 

}
</pre>  
* **Success Response:**

	Code: 200 

* **Error Response:**

	Code: 400 NOT FOUND
	
* **Content:**<br />
	
<pre>
{
	{
    "Message": "The request is invalid.",
    "ModelState": {
        "model.FileName": [
            "The FileName field is required."
        ]
    }
}
</pre>
