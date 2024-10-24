## 什么是自动化测试
Automation testing is a software testing technique where automated tools and scripts are used to execute pre-defined test cases instead of performing them manually. Efficiency, reusability and reliability.

## 什么时候开始自动化测试
I think we need to consider when to start automated testing when we start planning the project, and the earlier you start, the better. Although the initial investment in automated testing is relatively large, 
the sooner you get through the early stages, the sooner you can ensure product quality in a more efficient way. Considering the allocation of resources, it is impossible to invest too much in the early stages, 
but we can start with something like unit testing.

## 什么情况适合自动化测试
Repetitive tasks, data entry tasks, performance testing, work on multiple platforms, configurations

## 什么情况不适合自动化测试
Exploratory Testing, ad-hoc testing, test based on human subjective consciousness(user interface testing)
short-term projects, frequently changing features, one-time or rarely repeated tests

## 自动化测试框架
A set of guidelines, tools, and practices that provide a structured approach to creating, executing, and maintaining automated test scripts. It is the foundation upon which test automation is built, 
making it easier to develop and manage test cases efficiently and consistently.

## 自动化框架好处
reusability of code, improve test efficiency, higher test coverage, reduce manual effort, scalability, maintainability, integration with other tools, enhanced debugging and reporting

## 好的自动化测试框架
A good test automation framework should ensure efficiency, maintainability, and scalability of the testing process while allowing for collaboration between teams. It should support modularization, reusability, 
comprehensive reporting, integration with CI/CD pipelines, and robust error handling.

## 自动化框架组成部分
Test assertion tool, data setup, build management tool, CI/CD tool, Reporting tool, Logging tool

## 自动化测试框架开发挑战
1. Choosing the right tools and technologies that fit the application under test, the team's skill set, and the testing requirements can be difficult.
2. Ensuring that the framework is scalable enough to handle future growth in terms of test case numbers, platforms, browsers, and devices.
3. Modern web applications often have dynamic and asynchronous elements, which can be difficult to identify and interact with during test automation.
4. Frequent updates to the application under test can cause automated tests to break, leading to maintenance overhead.
5. Testing across multiple browsers, devices, and operating systems requires a framework that supports cross-platform testing, which can introduce complexity.

## 自动化测试指标
Time saved, Defects found, test coverage, maintenance time, test reusability, cost

## 好的自动化测试工具
Easy to use, compatible with platforms and OS, support multiple programming languages, integration with CI/CD tools, reporting and logging, scalability, community support and security

---------------------------------------------------------------------

## UI自动化流程
1. Requirement Analysis： Understand the requirements, specifications, user workflows, and functionalities of the application. objectives and scope.
2. Planning, design, development: Select automation tool(Selenium) and framework(data-driven,keyword-driven), setup test environment(Jenkins), create test scripts and other supported files.
3. Test execution and validation: run automated scripts, use assertions to do the validation.
4. Documenting test report, debugging and maintenance.

## UI自动化运行时长以及优化方法
Depends on several factors: usually minutes to hours
1. Number of test cases or size of test suite, including the complexity and structure of test scripts. - parallel execution, inefficient locators, unnecessary steps
2. environment setup(cloud-based,VM has extra delay) and automation framework optimization - well-maintained POM
3. Load time, network speed, wait time, Synchronization - use explicit waits over hardcoded sleep waits

## UI自动化占比，影响原因
The proportion of UI automation testing typically depends on the project's scale, complexity, development methodology, etc. Generally 30%.
1. Difficult to maintain: UI changes frequently, even small updates can cause scripts to break.
2. Slow execution: simulate real user interactions, loading time, element finding.
3. Limited coverage: primarily verifies interface layer, doesn't cover backend logic and data processes.

## 保证自动化测试稳定性
1. 合理化使用等待机制
2. 合理化异常处理机制
3. When multiple use cases are executed, reduce the coupling between use cases
4. 独立化测试环境
5. 确保元素定位的准确性

## 自动化测试常用库
Selenium WebDriver(browser automation), TestNG/JUnit(write and organize test cases), Log4j(logging details)

## 何时需要性能测试和自动化测试
Performance testing: early stage(identify potential bottlenecks), after deployment(ensure system handles expected loads), before releases.
Automation testing: during continuous integration whenever there is a code change, regression testing(to verify existing functionality works after code change)

## 封装浏览器方法(encapsulating browser methods)
you can achieve better code reuse and maintainability, reduce redundancy, and enhance the readability of your test scripts.
1. Create a class to handle browser startup, shutdown, and other basic operations. This class will encapsulate all browser-related actions.
2. Create a class and add methods to it for common actions.

## Selenium判断元素存在
findElements(), isDsiplayed(), findElement()with try-catch

## 如何定位动态元素
1. use other locators
2. use partial xpath
3. parent node, child node

## 浏览器操作
1. launch/close browser(driver.get(url) driver.quit()) 
2. navigate to urls(driver.navigate().to(url)) 
3. adjust size of window(driver.manage().window().minimize()) 
4. switch between browser tabs or windows(driver.switchTo().window()) 
5. refresh page(driver.navigate().refresh())
6. back/forward navigation(driver.navigate().back())
7. interact with browser elements(driver.findElement(By.name()))
8. enter inputs(driver.findElement(By.name()).sendKeys())
9. handle alerts and pop-ups(driver.switchTo().alert(),alert.accept())
10. take screenshots(driver.getScreenshotAs())
11. scroll page(JavascriptExecutor.executeScript())
12. handle cookies(driver.manage().addCookie())
13. handle browser timeouts(driver.manage().timeouts().implicitlyWait())

## 什么是Selenium,组成部分
Selenium is a widely used web automation tool that can help us to achieve browser automation and cross-browser testing.
Challenges: difficult to test image based application, need outside support for report generation, cannot perform SOAP, REST
Limitation: cannot test mobile applications, dynamic content, difficult to handle pop-ups, limited reporting.
Selenium IDE: Firefox/Chrome plug-in, to speed up the creation of automation scripts.
Selenium Remote Control: a server that allows users to write application tests in various programming languages.
Selenium Web Driver: a programming interface that helps create and run test cases.
Selenium Grid: used to distribute test execution on multiple platforms and environment concurrently

## Selenium内部结构（POM）
Page Object Model is a design pattern in test automation to create an Object Repository for web UI elements, a class holds functionalities.
Page Factory is an in-built page object model pattern used to initialize web elements which are defined in Page Objects.

## 脚本编写标准(best practices)
proper naming conventions, modularize code(resuable func, pom), regular commenting, error handling, exception management, assertions, parameterize tests, avoid hardcoding

## 自动化测试标准（best practices）
Define scope of automation early(what to automate, expectation)
select the right automation tool, choose an appropriate framework
follow scripting standards(脚本编写标准)

## Xpath定位元素/和//区别
A single slash represents an absolute path, requires explicit path
A double slash represents a relative path, selects nodes at any level in the document.

## TestNG
A testing framework based on JUnit and NUnit in order to simplify a broad range of testing needs starting from unit testing to integration testing

## Cucumber
Cucumber is a popular automation tool used for Behavior-Driven Development (BDD), 
which helps bridge the gap between technical and non-technical teams by allowing tests to be written in a language that both developers and business stakeholders can understand.
