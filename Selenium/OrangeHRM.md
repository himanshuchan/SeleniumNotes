### 🧱 **Project Overview: `OrangeHRMProject`**

| **Component**                  | **Location**         | **Purpose / Description**                                                                                                                                |
| ------------------------------ | -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Maven Config**               | `pom.xml`            | Core Maven file — manages dependencies (Selenium, TestNG, WebDriverManager, Log4j, ExtentReports), plugins, and build lifecycle. No manual JAR handling. |
| **Framework Engine Layer**     | `src/main/java`      | Core reusable logic, setup, and abstraction layer for all test components.                                                                               |
| → `com.orangehrm.actiondriver` |                      | Wraps WebDriver actions (`click`, `type`, `wait`) for stability and cleaner code.                                                                        |
| → `com.orangehrm.base`         |                      | Initializes WebDriver, loads configs, and handles setup/teardown. (`BaseTest`, `DriverManager`, `ConfigReader`)                                          |
| → `com.orangehrm.listeners`    |                      | Implements TestNG listeners for logging, screenshots, and retry mechanisms.                                                                              |
| → `com.orangehrm.pages`        |                      | Page Object Model classes — one per web page (`LoginPage`, `DashboardPage`, etc.). Contains locators and actions.                                        |
| → `com.orangehrm.utilities`    |                      | Common helpers (Excel, Wait, Log, Screenshot utilities) to avoid duplication.                                                                            |
| **Configuration Layer**        | `src/main/resources` | Stores all non-Java framework configs.                                                                                                                   |
| → `config.properties`          |                      | Environment variables (URL, browser, credentials, timeouts).                                                                                             |
| → `log4j2.xml`                 |                      | Logging configuration — defines log format, file output, and levels.                                                                                     |
| **Test Layer**                 | `src/test/java`      | Contains actual **TestNG test classes** (`LoginTest`, `EmployeeTest`). Extends `BaseTest`, uses Page Objects and utilities.                              |
| **Test Data & Suite Config**   | `src/test/resources` | Stores data and suite execution configs.                                                                                                                 |
| → `testdata/`                  |                      | Excel/JSON/CSV files for data-driven testing.                                                                                                            |
| → `testng.xml`                 |                      | Controls suite structure, test order, parallel execution, and grouping.                                                                                  |
| **Containerization**           | `docker/`            | Dockerfiles / Compose setups for Selenium Grid or Jenkins containers. Enables containerized CI runs.                                                     |
| **CI/CD Pipeline**             | `Jenkinsfile`        | Automates build → test → report → archive steps in Jenkins.                                                                                              |
| **Build Artifacts**            | `target/`            | Auto-generated folder with compiled `.class` files, reports, and logs. Never edited manually.                                                            |

---

### 🔥 **Summary by Layer**

|**Layer**|**Folder(s)**|**Purpose**|
|---|---|---|
|**Engine / Base**|`src/main/java`|Core framework logic & reusable modules|
|**Configuration**|`src/main/resources`|Config files & log settings|
|**Tests**|`src/test/java`|Actual automated test cases|
|**Test Data / Suites**|`src/test/resources`|Test data, `testng.xml` suite setup|
|**Artifacts**|`target`|Compiled code & reports|
|**CI/CD Integration**|`docker`, `Jenkinsfile`|Containerization & pipeline automation|
- What is config. properties file?
	- Used to define application-specific or framework-specific configuration details.
	- A configuration file that stores key-value pair.
	- Examples of properties stored:
		- Browser type (browser=chrome)
		  URL of the application (url=https://example.com)
		  Implicit/Explicit wait times (waitTime=10)
- Why do we need config. properties?
	- Centralized configuration: All critical settings in one place for easy management.
	- Ease of maintenance: Avoid hardcoding values in the codebase; update settings without modifying code.
	- Reusability: The same configuration file can be reused across multiple test case or modules.
	- Flexibility: Quickly switch between environments (eg QA, Staging, Production) by modifying a single file.
- What is BaseClass?
	- BaseClass is the backbone of the framework.
	- It contains common setup and teardown logic across all test cases.
	- Common functionality in BaseClass:
		- Initializing WebDriver.
		- Browser initialization and termination.
		- Loading configurations from config. properties.
		- Managing wait times.
- Why do we need BaseClass?
	- **Code Reusability**: Avoid duplicate setup/teardown code in each test class.
	- **Scalability**: Makes the framework easier to maintain and scale.
	- **Centralized control**: Any changes in test setup (e.g browser settings) can be applied globally from one class.
	- **Foundation for test execution**: Acts as a base for all test classes.
-  