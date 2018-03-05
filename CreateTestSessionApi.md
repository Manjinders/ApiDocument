**Administration Api**
----
Description : list of test.

* **URL**

  api/CreateSessionApi/TestList

* **Method:** 

    Get

* **Header:** 
    	
	Authorization: bearer your jwt token

* **Success Response:**

	Code: 200 
	
* **Content:**<br />
 
<pre>
{
[
    {
        "Name": "Test test",
        "Id": 1,
        "DateCreated": "22/02/2018",
        "TestStart": "2/22/2018 9:19:50 PM",
        "TestEnd": "2/22/2018 9:20:38 PM",
        "Timetaken": "0 hour 0 min ",
        "Notes": "Sorry I had to step away due to some emergency. I am back and done all the changes please review",
        "TestData": null,
        "Linktozip": "a6b2e733-90d3-49fe-afe3-a05e4e33b0eb.pdf"
    },
    {
        "Name": "Firstname Singh",
        "Id": 5,
        "DateCreated": "22/02/2018",
        "TestStart": "2/22/2018 10:17:30 PM",
        "TestEnd": "2/22/2018 10:18:08 PM",
        "Timetaken": "0 hour 0 min ",
        "Notes": "this just once you done with all the classes let me see them please, I want to make sure I am not missing anything or that we don't have anything extra that is not needed",
        "TestData": null,
        "Linktozip": "973a2661-2305-4f52-a3ffdff8-bb5fb1389acc.rar"
    }
]
}
</pre>
* **Error Response:**

	Code: 403 Invalid credentials



**View test details Api**
----
Description :View test details.

* **URL**

    api/CreateSessionApi/View/{id}

* **Method:** 

    Get
* **Header:** 
    	
	Authorization: bearer your jwt token


* **Success Response:**

	Code: 200 
	
* **Content:**<br />
 
<pre>
{
    "Name": "Test test",
    "Id": 1,
    "DateCreated": "02/22/2018",
    "TestStart": "2/22/2018 9:19:50 PM",
    "TestEnd": "2/22/2018 9:20:38 PM",
    "Timetaken": "0 hour 0 min",
    "Notes": "Sorry I had to step away due to some emergency. I am back and done all the changes please review",
    "TestData": "<p>public ActionResult token(string id)</p><p>&nbsp; &nbsp; &nbsp; &nbsp; {</p><p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;CreateSessionModel model = new CreateSessionModel();</p><p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; var resultModel = examsession.ValidateToken(id);</p><p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; if (resultModel.status)</p><p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; {</p><p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; return RedirectToAction(\"Index\", \"TechnicalTest\", new { name = resultModel.Data.FirstName + \" \" + resultModel.Data.LastName, examDetailId = resultModel.Data.ExamDetailId });</p><p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; }</p><p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; else</p><p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; {</p><p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ViewBag.ErrorMessage = resultModel.message;</p><p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; return View(\"Error\");</p><p>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; }</p><p>&nbsp; &nbsp; &nbsp; &nbsp; }</p>",
    "Linktozip": "a6b2e733-90d3-49fe-afe3-a05e4e33b0eb.pdf"
}
</pre>
	
* **Error Response:**

	Code: 400 NOT FOUND

* **Content:**<br />
	
<pre>
{
    "Message": "Test Not Found"
}
</pre>


** Create Test Session  Api**
----
Description :Create test session.

* **URL**

    api/CreateSessionApi/Create

* **Method:** 

    Get
	
* **Header:** 
    	
	Authorization: bearer your jwt token

* **Data Params** <br />

<pre>
{
	email   {String} *Required User's email address.
	First Name  string *Required.
	Last Name        {String} *Required.
	Notes {String} *Required password.

}	 
</pre>   

* **Example:** <br/>

<pre>
{
	"email":"test@gmail.com",
	"FirstName":"xyz",
	"Last":"abc",
	"Notes":"fdgd fghfg",

}
</pre>  
* **Success Response:**

	Code: 200 
	
	
* **Content:**<br />
 
<pre>
{
   localhost/api/CreateSessionApi/ValidateToken/e5c627a8-d8d5-4897-8065-9297fbb85219"
}
</pre>
	
* **Error Response:**

	Code: 400 NOT FOUND

* **Content:**<br />
	
<pre>
{
    "Message": "The request is invalid.",
    "ModelState": {
        "model.FirstName": [
            "The First Name field is required."
        ],
        "model.Email": [
            "The Email field is required."
        ],
        "model.LastName": [
            "The Last Name field is required."
        ],
        "model.Notes": [
            "The Notes field is required."
        ]
    }
}
</pre>


**Validate Token  Api**
----
Description :ValidateToken test session token.

* **URL**

    api/CreateSessionApi/ValidateToken/token

* **Method:** 

    Get
	
* **Header:** 
    	
	Authorization: bearer your jwt token


* **Success Response:**

	Code: 200 
	
	
* **Content:**<br />
 
<pre>
 {
    "Id": 0,
    "FirstName": "xyz",
    "Email": null,
    "LastName": "abc",
    "Notes": null,
    "ExamDetailId": 27
}
</pre>
	
* **Error Response:**

	Code: 403 Invalid credentials
