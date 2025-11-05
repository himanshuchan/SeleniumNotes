- Application programming interface-API acts as a middle layer or a interface between client and server.
    - Lets say we have a website called as marriot.com . If I want to buy tickets from marrriot.com of marriot hotel then there is no issue. UI can access the code if they are written in same language.
        - Case-1: When both front end and backend has same language base.
        - ![Exported image](Exported%20image%2020250822043529-0.png)
        - Case-2: When both have same language base but backend and front end does not belong to same organisation
        - ![Exported image](Exported%20image%2020250822043531-1.png)
            - Solution - marriotte can expose their API as there is no code in it. It is just an interface and hotels.com can use that interface to send and receive response from mariotte website.￼
            - ![Exported image](Exported%20image%2020250822043533-2.png)
        - Case-3: When both front end and back end belongs to same organisation but code base or stack is different.
        - ![Exported image](Exported%20image%2020250822043536-3.png)
            - Solution-- we are sending data in the form of json or xml which are both independent of any language. Json and xml are representation of data in specific format and almost every language has libraries to parse these files. Lets say I send first name and last name over http protocol to API through JSON. Dev makes API in such a way that when user hit the API, it captures the information and sends it to createReservation() method. Now this method will send output to API which then sends response to Frontend in json or xml format which will then be parsed by Typescript to show the data.
                - ![Exported image](Exported%20image%2020250822043541-4.png)
                - This Marriotte API will be hosted in the same server as marriotte.com.
                - Every organization will be getting their own api key. Eg Hotel.com , makemytrip.com etc etc will all get their own unique api key so that a hacker cannot go and book tickets. That key is used to identify if the request is genuinely made by hotel.com or makemytrip.com.
    - ![What is the API Client Waiter Act as API Chef](Exported%20image%2020250822043547-5.png)
    
    |   |   |   |
    |---|---|---|
    |**Term**|**Analogy Example**|**Real-World Role**|
    |**API**|The menu|Interface that defines what you can do|
    |**Web Service**|Calling to place an order|Using the API over the web (HTTP)|
    |**Microservice**|The pizza or dessert chef|Independent service that does one job|
    
    - RestAPI are faster than SOAP API.
    - Postman is a manual api testing tool. It is available in Desktop and web. Purpose of postman is to develop and test API.
    - Postman uses javascript as its scripting language for test automation.
    - The pre request script tab allows users to write javascipt code that runs before the main request, useful for setup tasks like setting variable or cleaning up data.
    - ==Collection is group of request.==Collection contains folders and http request.
    - Request--------\>API---------\>Response
    - GET- retrieves the resource from the database
    - POST-create new resource on database
    - PUT-update existing resource on database
    - DELETE-Delete existing resource from database
    - [https://www.reqres.in/api/users?page=2](https://www.reqres.in/api/users?page=2)------ query parameter. ? Is like a filter.
    - [https://www.reqres.in/api/users/2](https://www.reqres.in/api/users/2)------ path parameter
      
    - ![Exported image](Exported%20image%2020250822043552-6.png)
    - Rest(**RE**==presentational== **S**==tate== **T**==ransfer (REST)==
        - ==Rest is preferred to the more robust== **Simple Object Access Protocol (SOAP)** ==technology because REST uses less bandwidth, simple and flexible making it more suitable for internet usage.==
        - ==99% of the time body will be json.==
        - ==Rest assured is an API through which we can automate rest API.==
    - ==End point==: Address where API is hosted on the Server.
        - HTTP methods which are commonly used to communicate with Rest API’s are
        
        **GET, POST, PUT, and DELETE --CRUD operation(Create,Read,Update and Delete)**
        
        - **GET**- The GET method is used to extract information from the given server using a given URL. While using GET request, it should only extract data and should have no other effect on the data. No Payload/Body required. Retrives the resource from database.
            - **How to send input data in GET?**
        
        Ans: Using Query Parameters
        
        - **POST**- A POST request is used to send data to the server, for example, customer information, file upload, etc. using HTML forms. Create new resource on database. Eg creating reservation
            - **How to send input data in POST?**
        
        Ans: Using Form Parameters /Body Payload
        
        - **PUT**- Replaces all current representations of the target resource with the uploaded content. Update existing resource on database.
        - **DELETE**- Removes all current representations of the target resource given by a URI. Delete existing resource on database.
        - **Resources****: Resources basically represent API/Collection which can be accessed from the Server**
        
        ==Google.com==/==maps== -- maps,search,images is a resource here. Green is base url. Here google.com is as end point or server.  
        google.com/==search==  
        google.com/==images==
        
    - API Status:
        - 200 - Ok,Request successful. The server has responded as required.
        - 204- Ok, No content. When you use get after deleting the record.
        - 400
          
          
        
    - **Parameters in url:**
        - **Path parameters** are variable parts of a URL path which keeps on changing for every API request. They are typically used to **point to a specific resource within a collection**, such as a user identified by ID.
        
        [https://www.google.com/Images/](https://www.google.com/Images/1123343)==1123343==  
        [https://www.google.com/docs/1123343](https://www.google.com/docs/1123343)  
        [https://amazon.com/orders/112](https://amazon.com/orders/112)  
        [https://www.google.com/search?q=newyork&oq=newyork&aqs=chrome..69i57j0l7.2501j0j7&sourceid=chrome&ie=UTF-8](https://www.google.com/search?q=newyork&oq=newyork&aqs=chrome..69i57j0l7.2501j0j7&sourceid=chrome&ie=UTF-8)
        
        - **Query Parameters****:**
        
        Query Parameter is used to sort/filter the resources.  
        Query Parameters are identified with?””  
        [https://amazon.com/orders](https://amazon.com/orders?sort_by=2/20/2020)==?sort_by=2/20/2020==
        
    - **Headers/Cookies**:
        
        Headers represent the meta-data associated with the API request and response. In layman terms, we were sending Additional details to API to process our request.  
        Headers-tells the server the format of data being sent.  
        Example : Authorization details
        
        - **End Point Request URL can be constructed as below**
        
        ==Base URL/resource/(Query/Path)Parameters==
        
    - ==Post is a superset.== You can also use POST instead of delete,put.
    - Key is hardcoded.
    - JSON(Java script object notation). Json is faster than xml. SOAP API uses xml.
    - ==Google Maps Add API (POST):== ==adding something into the server. If you are starting a business and wants to show your location on maps then we can use this api to post our location to google maps. Similarly we can delete and update the location as well.==
    
    This API Will add new place into Server  
    **Complete URL :** ==https://rahulshettyacademy.com==**/maps/api/place/add/json?key= qaclick123**  
    **Base URL**==:== ==https://rahulshettyacademy.com==  
    **Resource**==:== ==/maps/api/place/add/json==  
    **Query Parameters**==: key =qaclick123 //====key ke baad koi space nai ayega wrna output 1 ho jayega==  
    **Http Method**==:== ==POST==  
    **Sample Body** ==:==  
    =={==  
    =="location": {==  
    =="lat": -38.383494,==  
    =="lng": 33.427362==  
    ==},==  
    =="accuracy": 50,==  
    =="name": "Frontline house",==  
    =="phone_number": "(+91) 983 893 3937",==  
    =="address": "29, side layout, cohen 09",==  
    =="types": [==  
    =="shoe park",==  
    =="shop"==  
    ==],==  
    =="website": "====http://google.com====",==  
    =="language": "French-IN"==  
    ==}==  
       
    **Sample Response**  
      
    =={==  
    =="status": "OK",==  
    =="place_id": "928b51f64aed18713b0d164d9be8d67f",==  
    =="scope": "APP",==  
    =="reference": "736f3c9bec384af62a184a1936d42bb0736f3c9bec384af62a184a1936d42bb0",==  
    =="id": "736f3c9bec384af62a184a1936d42bb0"==  
    ==}==  
    Got this for postman in my system- d468ec0afbb270d5de263267b644f8b1
    
      
      
    
    ==Google Maps Delete API (POST):==  
    ==This API Will delete existing place from Server==  
    **Complete URL**==:== ==https://rahulshettyacademy.com/maps/api/place/delete/json?key=qaclick123==  
    **Base URL**==:== ==https://rahulshettyacademy.com==  
    **Resource**==: /maps/api/place/delete/json==  
    **Query Parameters:** ==key==  
    **Http request** ==: DELETE==  
    **Sample Body** ==:==  
    =={==  
    =="place_id":"928b51f64aed18713b0d164d9be8d67f"==  
    ==}==  
    **Sample Response**  
    =={==  
    =="status": "OK"==  
    ==}==  
    ==Google Maps get Place API (GET):== ==to read==  
    **This API Will get existing place details from Server**  
    **Complete URL :** ==http://rahulshettyacademy.com/maps/api/place/get/json?place_id=xxxx&key=qaclick123==  
      
    **Base URL**==:== ==https://rahulshettyacademy.com==  
    **Resource**==: /maps/api/place/get/json==  
    **Query Parameters**==: key, place_id //( place_id value comes from Add place response)==  
    **Http request**==: GET==  
    ==Note: Key value is hardcoded and it is always qaclick123==  
    **Sample Response for the Provided Place_Id**  
    =="lat" : -38.383494,==  
    ==}==  
    ==Google Maps Put Place API (PUT):== ==for updating with new details==  
    This API Will update existing place in Server with new values  
    **Complete URL :** [https://rahulshettyacademy.com/maps/api/place/update/json?key=qaclick123](https://rahulshettyacademy.com/maps/api/place/update/json?key=qaclick123)  
    **Base URL** ==:== ==https://rahulshettyacademy.com==  
    **Resource**==: /maps/api/place/update/json==  
    **Query Parameters**==: key==  
    **Http Method**==: PUT -==  
    ==Note: Key value is hardcoded and it is always qaclick123==   
    **Sample Request:**  
    =={==  
    =="place_id":"8d2573bdf6ceec0e474c5f388fa917fb",==  
    =="address":"70 Summer walk, USA",==  
    =="key":"qaclick123"==  
    ==}==   
    **Sample Response for the Provided Place_Id**  
    =="lat" : -38.383494,==  
    ==}==
    

**Library API:**  
==Base URI:== ==https://rahulshettyacademy.com==  
==(or)== ==http://216.10.245.166==

- **Method**==: POST==

**Add Book Complete URL** - [https://rahulshettyacademy.com/Library/Addbook.php](https://rahulshettyacademy.com/Library/Addbook.php)  
   
aisle value should be number only. Isbn should be unique to insert. So provide random isbn which makes unique  
**Input Payload: Json**==:==  
=={==  
   
=="name":"Learn Appium Automation with Java",==  
=="isbn":"bcd",==  
=="aisle":"227",==  
=="author":"John foe"==  
==}==  
   
**Output Json**   
=={==  
=="Msg": "successfully added",==  
=="ID": "bcd227"==  
==}== 

- **Resource** ==: /Library/GetBook.php====?AuthorName=somename== **Method** ==: GET== 

   
**Output Json**==:==  
==Output the array of Json object books with all below details==   
 =={==  
 ==Name : “bookname”   ( String)==  
==Isbn :  “A2fdsf”   (String)==  
==Aisle : 32 (Integer)==  
 ==}==

- **Resource**==: Library/GetBook.php?ID=3389      -== **Method** ==: GET== 

**Output Json:**  
=={==  
=="book_name": "Selenium automation using Java",==  
=="isbn": "a23hd738",==  
=="aisle": "1223"==  
==}== 

- **Resource** ==:/Library/DeleteBook.php==      **Method** ==: POST==

**Input Payload: Json:**  
=={==   =="ID" : "a23h345122332"==   ==}==   
**Output Response**==:==  
=={==  
==msg : book is successfully deleted”==  
==}==  
Automation Scenarios to Test Library API -  
   
Verify if API responses returns Success Codes with Proper Assertions  
Verify if Response Json Schema is displayed as expected  
Create Environment/Global/Collection variables to dynamically switch end points of APIs to test in different stages of QA Life cycle  
Pass response ID of Add Book to Get Book and Delete ID request Parameters for full functional Automation Testing  
Validate the book ID response calculation Logic  
Validate if Get Book API retrieves the correct response with Book Details requested  
Validate if Delete Book API successfully deleted Book  
Implement Try Catch Error Handling Mechanism for every Automation test as Tear Down Script  
If Book Already exists in DB, Implement Smart Strategy to delete the existing Book first before Adding the Book again as Prerequisite Automation Step  
Parse the complete Json response and verify if the values are displayed as expected  
Generate Unique ISBN/ aisle value for every run to make Book Unique using Automation Script  
Import the Book Details from CSV/Json without hard coding for Validating API’s  
Run the APIs with multiple data sets by iterating the data from the CSV as a Data driven testing  
   
//  
What are Environments and variables in Postman?  
==An environment is a set of== ==variables== ==you can use in your Postman requests. You can use environments to group related sets of values together and manage access to shared Postman data if you are working as part of a team.==  
   
==Variables allow you to store and reuse values in your requests and scripts. By storing a value in a variable, you can reference it throughout your collections, environments, and requests—and if you need to update the value, you only have to change it in one place. Using variables increases your ability to work efficiently and minimizes the likelihood of error.==  
==How to use Environments and Variables in Postman?==  
   
==Variable scopes==

- ==Global==
- ==Collection==
- ==Environment==
- ==Data==
- ==Local==

==Scripting in Postman==  
==Postman contains a powerful runtime based on Node.js that allows you to add dynamic behavior to requests and collections. This allows you to write test suites, build requests that can contain dynamic parameters, pass data between requests,== 

![Diagram Description automatically generated](Exported%20image%2020250822043554-7.png)

The pm object  
==You will carry out most of the Postman JavaScript API functionality using “pm” which provides access to request and response data, and variables.==  
   
==Verify if there is an entry called Cypress.==  
==Verify if Cypress entry has course Title and Price properties/keys==  
==Verify if sum of API Courses equals to 90==  
==Verify if Web Automation Course titles are shown as expected titles==  
 **Postman can also test Soap Webservices in addition to Rest HTTP requests**  
==How Soap Webservices are different from Rest Services?==  
==Rest API’s use HTTP protocol to send the request and receive the response==  
==Whereas Soap Webservices/API’s use Soap Protocol to send the request ad receive the response==  
==In Soap Services, requests/responses are sent in XML Format.==  
==What will we learn from this Course?==  
==How to Call Soap Services from Postman- Understand the rules of setting up Soap Project in Postman==  
==How to write automation tests on the XML response of Soap Services.==  
   
Soap End Point example  
[https://www.dataaccess.com/webservicesserver/NumberConversion.wso](https://www.dataaccess.com/webservicesserver/NumberConversion.wso)  
What is Newman?

-  ==Newman is a command line Collection Runner for Postman.==
- ==It allows you to run and test a Postman Collection directly from the command line.==
- ==Using Newman, you can easily integrate it with your continuous integration servers and build systems.== 
- ==Newman is built on Node.js. To run Newman, Install Node.js as prerequisite.==
- ==After Node.js install, Install Newman from npm globally on your system, which allows you to run it from anywhere.====￼====npm install -g newman==
- ==How to run collection from Newman?==

==$ newman run \<CollectionFile\>==

- ==Learn about Newman Configuration options==
 - ==Generate HTML reports for Test execution results with newman - htmlextra plugin====￼====https://www.npmjs.com/package/newman-reporter-htmlextra== - ==Integrate Postman Automation Scripts to Jenkins CI/CD with the help of Newman commands==
- Trigger the Postman Automation Scripts from Terminal with the help of Newman CLI

Integrate the Automation Tests with Jenkins for CI/CD Implementation  
Prepare neat HTML reports for the Postman API Test Automation results  
Understand how to collaborate as a Team by forking the existing Project – Creating branches- Creating Pull requests – Merging  
 
 - ==What is Rest Assured?==
    
    - ==Rest assured is a java based library that is used to test RESTful Web services/API.==
    - ==This is a java jar which we use in our project for validation.==
- ==Advantages of maven==
    
    - ==Automatic standard skeleton project creation==
    - ==Ease of adding project dependencies== ==-\>mvnrepository.com==
    - ==Seamless integration with CI/CD.==
    - ==Artifact id is nothing but your project name==
    - ==Group id is parent of the project==

import io.restassured.RestAssured;  
import static io.restassured.RestAssured.*;
 
public class Basics {
 
}

- How are RESTAPI is stateless?
    - REST architecture requires that client's state is not stored on the server.
- Explain the HTTP methos?
- How to parse complex json?￼This is an example of mock or dummy api response. In real life you will have to parse json from the api itself.
-   
    
       
=={==  
=="location":{==  
=="lng" : 33.427362==  
==},==  
=="accuracy":50,==  
=="name":"Frontline house",==  
=="phone_number":"(+91) 983 893 3937",==  
=="address" : "29, side layout, cohen 09",==  
=="types": ["shoe park","shop"],==  
=="website" : "====http://google.com====",==  
=="language" : "French-IN"==  
=={==  
=="location":{==  
=="lng" : 33.427362==  
==},==  
=="accuracy":50,==  
=="name":"Frontline house",==  
=="phone_number":"(+91) 983 893 3937",==  
=="address" : "29, side layout, cohen 09",==  
=="types": ["shoe park","shop"],==  
=="website" : "====http://google.com====",==  
=="language" : "French-IN"==  
==Postman supports the following variable scopes:==
       

public static void main(String[] args) {  
// TODO Auto-generated method stub  
//Validate if Add place API is working as expected  
//given- All input details  
//when- submit the API --only resource and http method will come under when  
//then- Validate the response  
RestAssured.baseURI="https://rahulshettyacademy.com";  
given().log().all().queryParam("key","qaclick123").header("content-type","application/json")  
.body(" {\r\n" //Eclipse automatically converts json to string  
+ " \"location\": {\r\n"  
+ " \"lat\": -38.383494,\r\n"  
+ " \"lng\": 33.427362\r\n"  
+ " },\r\n"  
+ " \"accuracy\": 50,\r\n"  
+ " \"name\": \"Himanshu Baunthiyal\",\r\n"  
+ " \"phone_number\": \"(+91) 983 893 3937\",\r\n"  
+ " \"address\": \"29, side layout, cohen 09\",\r\n"  
+ " \"types\": [\r\n"  
+ " \"shoe park\",\r\n"  
+ " \"shop\"\r\n"  
+ " ],\r\n"  
+ " \"website\": \"http://rahulshettyacademy.com\",\r\n"  
+ " \"language\": \"French-IN\"\r\n"  
+ " }\r\n"  
+ "").when().post("maps/api/place/add/json")  
.then().assertThat().statusCode(200);  
}
 
{  
"dashboard": { //dashboard and courses are nodes  
"purchaseAmount": 910, //purchaseAmount and website are child nodes  
"website": "rahulshettyacademy.com"  
},  
"courses": [ //whenever you see square brackets in json it means it is an array  
{ //  
"title": "Selenium Python", //selenium python,cypress and rpa are child nodes.  
"price": 50,  
"copies": 6  
},  
{  
"title": "Cypress",  
"price": 40,  
"copies": 4  
},  
{  
"title": "RPA",  
"price": 45,  
"copies": 10  
}  
]  
}  
==1. Print No of courses returned by API==  
==2.Print Purchase Amount==  
==3. Print Title of the first course==  
==4. Print All course titles and their respective Prices==  
==5. Print no of copies sold by RPA Course==  
==6. Verify if Sum of all Course prices matches with Purchase Amount==