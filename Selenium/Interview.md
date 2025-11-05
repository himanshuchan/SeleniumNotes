1. What is selenium?
    
    Selenium automates the browser.
    
    - Selenium IDE
    - Selenium Webdriver- introduced from selenium 2-
    
    Selenium webdriver is a java interface which contains n number of abstract methods and variables. That webdriver interface is implemented by multiple classes like chrome driver class,firefox driver class and edge driver class etc.  
    We can say that Webdriver is also a API(Application programming interface).API contains n number of classes and methods by which we can communicate with client and the server.  
    Webdriver is one of the component is selenium suite.  
    Selenium webdriver supports multiple languages. It supports many operating system. It is open source. But it does not support excel files(but can be done using apache POI library),report generation is not there but can be done by Extent report and Allure report. It can’t automate windows application(But can be done using third party tool like AutoIT). Graphs cannot be automated using selenium.
    
    - Selenium Grid- used to execute our test cases in remote environment
    - Selenium RC- depricated from selenium 3
2. What is architecture of selenium webdriver?
    - ![Exported image](Exported%20image%2020250822043410-0.png)
    - W3C has replaced JSON wire protocol from selenium 4.
    - In JSON wire protocol encoding and decoding is required when sending request to the drivers.
    - W3C(world wide web consortium)-there is no encoding or decoding concept. As driver,client libraries,browsers are already following w3c protocol there will be much more stability and consistency. Additional features like action API like zoom out,zoom in,keyboard actions are added because of w3c standard. In 3.11 w3c standard was introduced.
3. Difference between driver.findElement() and driver.findElements()?
    - Driver.findElement() returns the first web element matching the provided locator while driver.findElements() returns a list of all elements that matches the locator.
4. Difference between driver.close and driver.quit commands?
    - The driver.close() command is used to close the current tab/window of the browser which is controlled by the Selenium Webdriver.
    - The driver.quit() closes all browser windows and ends selenium webdriver session.
5. What are the challenges with Selenium Automation?
    1. No Support for Non-Web Automation
    2. Timeout or sync issues
    3. Test execution slowness in internet explorer
    4. Limited reporting
6. What are selenium 4 features?
    1. Webdriver is developed completely by W3C standardization.
    2. The Selenium IDE support for Chrome is available now.
7. How to count number of links in the webpage?
    1. Count the number of anchor tags. Eg driver.findElement(By.tagName("a").size());
8. What is RestAPI(**Re**presentational **S**tate **T**ransfer **A**pplication **p**rogramming **i**nterface)?
    1. API-it is a way for two computers to talk to each other
    2. Rest API- The common API standard used by mobile and web application to talk to the server is called as Rest API.
    3. Rest is not specification but set of rules.
    4. API which follows Rest standard is called Restful API.
9. What are ACID properties?￼[https://www.youtube.com/watch?v=GAe5oB742dw&list=PLCRMIe5FDPsdnSszazqVIQFh99t1ExH19&index=6](https://www.youtube.com/watch?v=GAe5oB742dw&list=PLCRMIe5FDPsdnSszazqVIQFh99t1ExH19&index=6)￼To maintain the integrity of the database 4 properties are described in the database
10. ![Exported image](Exported%20image%2020250822043413-1.png)
    1. Atomicity-All or nothing. If I transfer 100rs to some account and it gets debited from my account but does gets credited into another then whole transaction will be nulled. Atomicity ensure that both updates either happen together or not at all.
    2. Consistency- eg I have 50 rs in bank and I want to withdraw 100 rs then it will be a consistency violation and transaction will be cancelled.
    3. Isolation - even after millions of concurrent transactions every transactions are isolated. I can't withdraw from someone's account.
    4. Durability- Once a transaction is done it will be permanently saved even I case of system failure.

API Testing Tips for QA Engineers  
Mastering backend validation like a pro.
 
1. Unauthorized Access to Restricted Endpoints  
* What to Do: Try accessing protected endpoints as a non-privileged user.  
* Expected Result: Should return 403 Forbidden.  
* Bonus Edge Cases:  
* Expired Token → 401 Unauthorized  
* Invalid Token → 401 Unauthorized
 
2. 200 OK But No Response Body?  
* Check Requirement: Should there be data?  
* If yes → File a bug  
* If no data is expected → Should return 204 No Content
 
3. Can't See Newly Created User (GET Issue)  
* Steps:  
1. Confirm POST was successful (201 Created)  
2. Check DB directly  
3. Validate pagination (e.g., only 50 users per page)
 
4. Invalid Request Returns 200?  
* Not OK: Bad input should not return 200 OK  
* What to Do:  
* Report as bug  
* Expect proper codes like 400 Bad Request or 422 Unprocessable Entity
 
5. Test Rate Limiting  
* Steps:  
* Send 100 requests/minute → Should pass  
* 101st request → Should return 429 Too Many Requests  
* Wait for the time window to reset → Retry
 
6. Simulate Two Users Updating Same Record  
* Goal: Detect race conditions  
* Expected Behavior:  
* Server should lock or manage conflicts (e.g., optimistic locking)  
* Second update should wait or fail gracefully
 
7. Handling 500 Internal Server Errors  
* Steps:  
1. Get access to server logs/tools (e.g., New Relic, Datadog)  
2. Track request timestamp + endpoint  
3. Analyze error stack for root cause
 
8. Mock API Responses  
* Use When: Backend is not ready or unstable  
* Tools: Postman (Mock Server), WireMock, Mockoon  
* Benefit: Test frontend or client integration early
 
9. Monitor for API Slowdowns  
* Track Metrics: Response time trends  
* Tools: Datadog, New Relic, Postman Monitors  
* Trigger: Alert if response time increases over time
 
10. Find Access Tokens in Browser  
* How:  
* Local Storage → DevTools \> Application tab  
* Network Tab → Check login API response  
* Console → window.localStorage.getItem('tokenKey')
 
11. Validate JSON Schema  
* Use tools like JSON Schema Validator  
* Helps ensure consistent structure in response fields
 
12. Check for Missing Fields or Nulls  
* Validate each key-value pair  
* Edge Case: Fields should not be missing or randomly null without reason
 
13. Test with Realistic & Edge Data  
* Use valid, invalid, empty, too long, and special character data  
* Helps catch validation gaps
 
14. Automate Regression with API Tests  
* Use tools like RestAssured, Postman (Collection Runner), or Karate  
* Automate common flows (login, create, update, delete)
 
15. Test Caching Behavior  
* Repeated GETs → Are they faster?  
* Use headers like Cache-Control, ETag, If-None-Match  
* Verify cache hits vs. misses