**什么是接口测试**
API Testing is a type of software testing that focuses on verifying the interactions and data exchanges between different components or services within a software system. 
It aims to ensure that APIs perform correctly, reliably, and efficiently.

**接口测试流程(API testing process)**
1. Understand API requirements(e.g. request methods, authentication mechanisms, response formats), define testing scope and objectives.
2. Choose the frameworks and tools.
3. Design test cases, set up test data and test suites based on the specifications.
4. Test execution: test environment setup, execution via tools.
5. Test result validation: validate response(status code, response body etc), error and exception handling.
6. Documentation: Log test execution result, generate reports for tracking

**无接口文档如何保证正确性(Make sure correctness without API document)**
1. Engage with the API developers or stakeholders to gather essential information.
2. Reverse engineering: check the source code to understand how the API is called and what data is sent or received. check developer tools if browser.
3. Exploratory testing(test strategy), send requests and analyze responses to get better idea of the process.

**接口测试优缺点**
Early detection of bugs， faster execution， comprehensive coverage， stable
high cost on maintenance, difficult to debug compare to ui tests, dependency on third party services

**判断响应断言准确率(response assertion)**
1. Define clear expected results before running any tests.
2. Use assertions in test cases to validate the API response against expected results.
3. Use testing frameworks like JUnit, automation tools like Postman automatically check the accuracy.

**如何做接口数据驱动（data-driven testing**
To implement data-driven testing, test an API by feeding it multiple sets of data inputs and validating the outputs against expected results.
1. Identify test scenarios and variables.
2. Create data sets, store in csv/json.
3. Setup testing tool and write test cases that accept data sets as input.
4. Test execution and validation.
5. Analyze results and generate reports.

**测试数据获取(testing data)**
Mock data, external files(csv,json)

**数据驱动方法(data driven method)**
csv, excel, databases, json/xml

**报告(Report)如何介入Jenkins**
The process involves installing the necessary plugins, configuring the project to generate test reports, and adding post-build actions to publish them. Jenkins will generate visual summaries that provide insights into test performance and coverage.

**性能测试指标(best practices)**
1. Response time(from send to receive)
2. Throughput(number of requests within a specific time frame)
3. Concurrent users(active users/sessions same time)
4. Error rate
5. Resource Utilization(hardware resources being used)

**测试指标**
1. Test coverage: the precentage of code or functionality covered. all critical paths and use cases are covered, new features or changes are tested.
2. Defect Density: how many bugs or issues are found, campare against previous releases or industry standards.
3. Test execution metrics: number of test cases passed, failed, or blocked. majority of test cases are executed and passed, failed are fixed, blocked are documented and has a resolution.
4. Defect leakage and resolution time: no critical or high-priority issues left, end-users acknowledge of the exsiting issues, and there will be a resolution for each issue.

**交付指标**
1. on-time delivery 2. quality of delivery 3. number of defects after release goes alive 4. cost

**处理未通过测试**
1. Analyze failure logs, understand reason 
2. Try to find root cause: flaky test, examine test data, debug test script, test case steps, environment issue
3. Log the issue, prioritize the fix
4. Rerun the test document resolution

**测试计划**
1. Define test plan objectives, identify test scope
2. Determine test criteria, test strategy, test resources
3. Establish test schedule, specify test deliverables
4. Design test cases, define test environments
5. Risk management, review and update plan

**REST和SOAP区别**
Comparing SOAP vs REST API, SOAP only works with XML formats whereas REST work with plain text, XML, HTML and JSON.
SOAP requires more bandwidth for its usage. Since SOAP Messages contain a lot of information inside of it.

**什么是测试环境**
A test environment is a setup or configuration where software applications are tested to ensure they function correctly before being deployed to a production environment. 
It includes the hardware, software, network, databases, configurations, and any other system elements necessary to replicate the conditions under which the application will run in production.
