- Jason Huggins developed Selenium in 2004 while working in Thoughtworks.  
- Selenium scans from top left  
- If you declare a function as static then you don’t need to make an object of the class to access that function.  
- CSS is faster than xpath  
- <mark style="background: #FFF3A3A6;">Traversing from child to parent is not possible in CSS but possible in xpath  </mark>
- Absolute xpath depends on the parent nodes while relative xpath expression is independent of parent nodes  
- xpath allows to traverse forward from parent element to child element as well traverse back from child element to parent element.  
- A locator is an address for uniquely identifying web elements in a page.  
- Webdriver component of selenium is called as selenium 2  
- Selenium IDE(Integrated development environment)  
- Return type of findElement is void. Use findElement when asking for WebElement.  
- Return type of findElements is list  
- $('tagname.class') --for searching element in console using css.  
- $**x**('tagname.class') --for searching element in console using xpath.  
- We can change class name to CSS by putting dot (.) and for id we can put # .  
- ctrl+shift+/ - comments the selected lines in eclipse  
- ctrl+shift+O - adds missing links automatically and removes unused imports.  
- driver.get("http://google.com");//it **waits** for the full page load  
- Select dropdowns are static
- driver.navigate().to("https://rahulshettyacademy.com"); //navigates to the link. It **doesn't necessarily wait** for the full page load. Slightly faster than get().
- driver.navigate().back();//navigates back to google
- driver.navigate().forward();//navigates to rahul shetty website
- driver.navigate().refresh();//refreshes the page  
![Exported image](Exported%20image%2020250822043358-0.png)
- Synchronization
    - <mark style="background: #BBFABBA6;">Implicit wait</mark> - wait is declared globally-it is applicable in entire test case.
      eg driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(5));
        - Eg if I put a implicit wait condition to throw exception after 5 second and the result comes in 3 second then it will **not** wait for other 2 second.
            - Advantage- Code is readable and clean.
            - Disadvantage- hides performance issues .i.e Performance issues are not caught. Eg if I have put implicit wait of 5 second and in one step user wants wait to be not more than 2 sec then also test will pass. This will be a hidden bug.
    - <mark style="background: #BBFABBA6;">Explicit wait</mark> - wait is declared to target specific element
        - Webdriver wait- eg. WebDriverWait wait = new WebDriverWait(driver,Duration.ofSeconds(5));// we create 'w' object to use functions of WebDriverWait class.￼==w.until(ExpectedConditions.==visibilityofElementLocated(By.cssSelector("input.promocode")));//green tk common￼Polling interval-500milisecond(fixed) ￼**Exception handling**- handles "NoSuchElementException" by default.￼eg. WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10)); ￼wait.until(ExpectedConditions.elementToBeClickable(By.id("elementId")));
    - <mark style="background: #BBFABBA6;">Fluent wait</mark>-more flexible and allows customization. Polling interval is customizable. It tries to find the web element at regular intervals of time until the timeout or till the object gets found.￼**Exception Handling**: Can ignore any specified exceptions during the wait time.￼eg. FluentWait\<WebDriver\> wait = new FluentWait\<\>(driver) .withTimeout(Duration.ofSeconds(10)) .pollingEvery(Duration.ofSeconds(2)) .ignoring(NoSuchElementException.class); wait.until(ExpectedConditions.elementToBeClickable(By.id("elementId")));
            - Advantages of explicit wait: Wait is applied only at targeted elements. So no performance issues
            - Disadvantage: More code and more complex.
    - Can we use implicit wait everywhere?What's the use of explicit wait?
        - Let's say I want to page2 from page 1. Page 1 has three p tags and page 2 has one. I am searching the element in page 2 using p tag. Lets say I click on login so that I can go to page2. As selenium is very fast before the page2 loads it will try to search for the element in page 1 itlself and it will create an error that's why we need to explicitly define wait so that selenium can wait till page 2 loads and then can search the element.
- -ctrl+shft+f -- for formatting the code
- #**following siblling**- used in xpath for traversing to child sibling or you can say child nearby other child
- #Traversing from child to parent
    - WebElement input = driver.findElement(By.xpath("//label[text()='Name']/parent::div"))
- **Xpath****-** xpath mein sirf text aur contains mein @ nai aata
    - //htmltagname[@attribute='value'] ---- attribute mein bas ==id,class,name== use krenge bas
    - //htmltagname[@attibute='value' and @attribute='value']
    - //htmltagname[@attibute='value'][index]-- in case of mutiple elements coming in xpath only. Moving to the nth index
    - //htmltagname[starts-with(@attribute,'value')]--jahan id ka kch part dynamic ho jo refresh marke change ho rha hai toh
    - //htmltagname[text()='value of text'] -- us case mein jahan exact text ho
    - //htmltagname[contains(text(),'value of the text')]
    - //htmltagname[contains(@attribute,'value of the attribute')] ----**Regular expression use in xpath**
    - //htmltagname[@attribute='value'] /htmltagname[@attribute = 'value'] -- jahan xpath ke ander jana ho #important
    - //parenttagname/childtagname --traversing from parent to child in xpath
    - //header/div/button[1]/parent:: div/button[2]
    - There is no css syntax to identify the element based on the text. This is unique and only applicable to xpath.
    - ==We can replace htmltagname with * in xpath and this will also work==
    - Absolute xpath- starting from the root like html and denoted by single slash
    - Relative xpath- starting with //
    - class="submit signInBtn" for a class with space between then
        - Driver.findElement(By.className("submit"));//if we are using classname locator then we can use any of the class name
        - Driver.findElement(By.xpath("//tagname[@class='submit signInBtn']));//if we are using xpath or css then we have to take full class name
    - //h2 --for making xpath out of a tagname xpath("//h2")
- **CSS selector**
    - \<input type="text" class="cs" placeholder="Username" id="inputUsername" value=" " \>
    - **#idname** ---- eg driver.findElement(By.cssSelector("#inputUsername")).click();//when you want to use idname in css selector
    - Tagname.classname--if you have a class and you want to derive css out of it **eg driver.findElement(By.cssSelector("input.cs"));** //here tagname is optional ".cs" will also work #important
    - Tagname#id--if you have a id and you want to derive css out of it eg **diver.findElement(By.cssSelector("input#inputusername"));**
    - Tagname[attribute='value'] --Used In case where html does not have classname or id. **Eg driver.findElement(By.cssSelector("input[placeholder='Username']"));**
    - If there is a class and have a space in between then just use dot. Eg . If class='himanshu baunthiyal' then css will be .himanshu.baunthiyal #important
    - htmltagname[attibute='value']:nth-child(nth) ----moving to the nth index in cssSelector
    - Htmltagname childtagname -- from ==traversing from parent to child==. xpath jaisa hi linkhna hai without slashes. Space dalna hai bas.
    - Tagname[attribut*='value'] -----in case jahan value dynamic ho . Eg value ke last k kuch digits change ho rhe hon. Value='Username12345' then css will be input[placeholder*='Userna']---**Regular expression use in cssSelector** #important
    - For using class in css selector- tagname.classname
		<p class="error "\>* Incorrect username or password \</p\>
	driver.findElement(By.cssSelector("p.error"));
    - Tagname //to make css out of tag name. eg h2 tagname cssSelector("h2")
- **Link text**-used when we have to click on a link
    - Eg \<a href="#"\>Forgot your password?\</a\>
        - Driver.findElement(By.linkText("Forgot your password")); 
import java.time.Duration;
 
import org.openqa.selenium.By;  
import org.openqa.selenium.WebDriver;  
import org.openqa.selenium.chrome.ChromeDriver;  
import org.testng.Assert;
 
public class Locators {
 
}

-   
    

**1. Static Dropdown -** options in this dropdown are fixed. Whenever you see select it is static dropdown.  
WebElement staticdropdown=driver.findElement(By.name("ctl00$mainContent$DropDownListCurrency")); //driver .findElement gives a WebElement.  
Select dropdown = new Select(staticdropdown);//used in case of static dropdown only . Select is a class in selenium.
dropdown.selectByIndex(3);  
System.out.println(dropdown.getFirstSelectedOption().getText());  
dropdown.selectByValue("AED");  
System.out.println(dropdown.getFirstSelectedOption().getText());  
dropdown.selectByVisibleText("INR");  
System.out.println(dropdown.getFirstSelectedOption().getText());
2. Auto suggestive dropdown
	1. 
 
#Assertion in Selenium  
-Assert.assertequals(actual,expected);  
#**Exceptions in Selenium Java**  
1.**NoSuchElementExceptio**n- occurs when an element cannot be found in the DOM (Document Object Model) of the page.  
-\>Causes: 
1. using locators incorrectly.  
2. Element not loaded - as automation tool will not wait till the page is loaded and will try to access the element which is not accessible yet then it will throw exception
3. element is present in different frame  
4. Page redirection- if page redirect to a different page then element is no longer available  
5. Timing issue- if webdriver attempts to interact with the element before it has fully loaded.  
	1. Eg. Let's say you want to select 4 th index in Select static dropdown and the index ends at 3 then it will throw this exception
	   ![[Pasted image 20250916021938.png]]
	2. Eg if i want to search an element and it is either not present or it's on another page then it throws this exception.
2.**ElementClickInterceptedException**- when other element is receivieng the click but not the actual button ie button is not clickable. This is a common error encountered while working with single page application like angular or react ie. Url is not changing when clicking on something but window is changing.  
\<div\>  
\<label\>Name\</label\>  
\<input type="text" id="username"/\>  
\</div\>  
WebElement input = driver.findElement(By.xpath("//label[text()='Name']/following-sibling::input"));//This finds the \<input\> that comes immediately after the \<label\> with text **"Name"**.  
Eg \<button class="logout-btn"\>Log Out\</button\>  
Xpath- //button[text()='Log Out']
3.**ElementNotInteractableException**- the element was found in the **DOM (Document Object Model)**, but Selenium **cannot interact** with it at that moment (can’t click, type, or perform action).
	- Eg. Lets say there is a tab and by clicking it there comes a pop up window. You write a code to do operation on that window but forgot to write code for clicking the tab itself then this pop up will come. Below i forgot to click on dropdown and wrote a code to add adult. Selenium couldn't interact with + sign as as of now this window is not visible to it.
	  ![[Pasted image 20250916021139.png]]
	- 	
      

public static void main(String[] args) throws InterruptedException  
{  
WebDriver driver = new ChromeDriver();// Webdriver is a class and driver is its object. Scope of the driver is in the class only. We can't call it directly outside of the class.  
Thread.sleep(1000);  
driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(5));//==to delay the selenium so that selenium can get the error text==  
//selenium will wait on every step with the given time for the text to show up  
driver.get("https://rahulshettyacademy.com/locatorspractice/");  
/*driver.findElement(By.id("inputUsername")).sendKeys("himanshu.sdet@gmail.com");  
driver.findElement(By.name("inputPassword")).sendKeys("sdettesting");  
driver.findElement(By.className("signInBtn")).click();  
Thread.sleep(1000);  
System.out.println(driver.findElement(By.cssSelector("p.error")).getText());//As error will come after sometime. It might happen that selenium tries to immediately get the text before it pops up. for that we have to implicit delay the selenium  
driver.findElement(By.linkText("Forgot your password?")).click();
 
//driver.findElement(By.xpath("//input[@placeholder='Name']")).sendKeys("himanshu");  
//driver.findElement(By.xpath("//input[@placeholder='Email']")).sendKeys("himanshu.sdet@gmail.com");  
//driver.findElement(By.xpath("//input[@type='text'][2]")).sendKeys("himanshu.sdet@gmail.com");//i==ndexing using x-path,when there are multiple lines with same attributes.==  
driver.findElement(By.cssSelector("input[type='text']:nth-child(2)")).sendKeys("himas.himanshu");//==indexing using css selector==  
driver.findElement(By.xpath("//input[@placeholder='Phone Number']")).sendKeys("123456789");  
driver.findElement(By.className("reset-pwd-btn")).click();  
//driver.findElement(By.xpath("//input[@placeholder='Name']")).clear();//to clear the field  
//driver.findElement(By.xpath("//*[@placeholder='Name']")).clear();--==in xpath only--* can be replaced with any tagname==  
//driver.findElement(By.className("go-to-login-btn")).click();  
//driver.findElement(By.className("ghost")).click();  
driver.findElement(By.xpath("//form/input[3]")).sendKeys("Testing");  
//driver.findElement(By.xpath)  
//driver.close();  
//System.out.println(driver.findElement(By.cssSelector(".infoMsg")).getText());  
System.out.println(driver.findElement(By.cssSelector("form p")).getText());  
driver.findElement(By.className("go-to-login-btn")).click();  
*/  
driver.findElement(By.xpath("//input[@id='inputUsername']")).sendKeys("rahul");  
WebElement footerdriver=driver.findElement(By.id("gf-BIG"));//==limiting webdriver scope to particular section==  
//driver.findElement(By.xpath("//input[@name='inputPassword']")).sendKeys("Testing");  
driver.findElement(By.cssSelector("input[type*='pass']")).sendKeys("rahulshettyacademy");  
driver.findElement(By.id("chkboxTwo")).click();  
driver.findElement(By.xpath("//button[contains(@class,'submit')]")).click();  
Thread.sleep(3000);  
//driver.findElement(By.className("logout-btn")).click();  
//Thread.sleep(1000);  
System.out.println(driver.findElement(By.tagName("p")).getText());  
Assert.assertEquals(driver.findElement(By.tagName("p")).getText(),"You are successfully logged in.");//==for using assertion==
      

}
- project-name/
- │
- ├── pom.xml                 ← Maven config (dependencies, plugins, etc.)
- │
- └── src/
-     ├── main/
-     │   ├── java/           ← contains packages. your **application (framework) source code**
-     │   └── resources/      ← config files, properties, data files
-     │
-     └── test/
-         ├── java/           ← your **test classes** (actual TestNG/Cucumber tests)
-         └── resources/      ← test-related configs (test data, feature files)
- 