## **什么是接口测试** <br/>
API Testing is a type of software testing that focuses on verifying the interactions and data exchanges between different components or services within a software system. 
It aims to ensure that APIs perform correctly, reliably, and efficiently.

## **接口测试流程(API testing process)**
1. Understand API requirements(e.g. request methods, authentication mechanisms, response formats), define testing scope and objectives.
2. Choose the frameworks and tools.
3. Design test cases, set up test data and test suites based on the specifications.
4. Test execution: test environment setup, execution via tools.
5. Test result validation: validate response(status code, response body etc), error and exception handling.
6. Documentation: Log test execution result, generate reports for tracking

## **无接口文档如何保证正确性(Make sure correctness without API document)**
1. Engage with the API developers or stakeholders to gather essential information.
2. Reverse engineering: check the source code to understand how the API is called and what data is sent or received. check developer tools if browser.
3. Exploratory testing(test strategy), send requests and analyze responses to get better idea of the process.

## **接口测试优缺点** <br/>
Early detection of bugs， faster execution， comprehensive coverage， stable
high cost on maintenance, difficult to debug compare to ui tests, dependency on third party services

## **响应时间过长 怎么检测和处理**
1. 性能测试工具：
使用性能测试工具（如 JMeter、LoadRunner、Gatling）来模拟多个用户并监控 API 响应时间。这些工具可以提供详细的报告和图表，帮助你识别性能瓶颈。
2. 自动化测试框架：
在自动化测试框架中（如 Postman、RestAssured、JUnit），你可以编写测试用例，测量 API 请求的响应时间，并设置阈值进行验证。
```
java
Copy code
long startTime = System.currentTimeMillis();
Response response = given().when().get("https://api.example.com/data");
long endTime = System.currentTimeMillis();
long duration = endTime - startTime;

assertTrue("Response time is too long!", duration < 2000); // 设定 2 秒为阈值
```
3. 集成监控：
将 API 响应时间监控集成到 CI/CD 流程中，确保在每次构建或发布时自动运行性能测试。

### 处理响应时间过长的问题
1. 分析响应时间：
在测试报告中，分析响应时间数据，识别哪些 API 调用响应时间过长，并与开发团队讨论可能的原因。
2. 设置警报机制：
在 CI/CD 流程中设置响应时间超出阈值的警报，以便团队能够及时响应。
3. 优化后端性能：
在发现响应时间问题后，与开发团队合作，分析后端代码、数据库查询和 API 设计，优化性能。
4. 缓存策略：
考虑使用缓存（如 Redis）来存储频繁访问的数据，减少数据库请求。
5. 负载均衡：
在负载增加时使用负载均衡策略，确保 API 能够处理大量请求。
6. 限流与降级：
实现限流机制，防止瞬时流量导致的性能下降。在流量过大时，使用降级策略返回默认或简化数据。

示例代码（Postman）
在 Postman 中，你可以使用 Tests 标签编写响应时间的测试：
```
javascript
Copy code
pm.test("Response time is less than 2000 ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(2000);
});
```
总结
通过以上方法，你可以有效地检测和处理 API 请求响应时间过长的问题，从而提升自动化测试的有效性和系统性能。与开发团队的紧密合作和实时监控机制的实施是确保高性能 API 的关键。

## **判断响应断言准确率(response assertion)**
1. Define clear expected results before running any tests.
2. Use assertions in test cases to validate the API response against expected results.
3. Use testing frameworks like JUnit, automation tools like Postman automatically check the accuracy.

## **如何做接口数据驱动（data-driven testing** <br/>
To implement data-driven testing, test an API by feeding it multiple sets of data inputs and validating the outputs against expected results. <br/>
1. Identify test scenarios and variables.
2. Create data sets, store in csv/json.
3. Setup testing tool and write test cases that accept data sets as input.
4. Test execution and validation.
5. Analyze results and generate reports.

## **测试数据获取(testing data)** <br/>
Mock data, external files(csv,json)

## **数据驱动方法(data driven method)** <br/>
csv, excel, databases, json/xml

## **报告(Report)如何介入Jenkins** <br/>
The process involves installing the necessary plugins, configuring the project to generate test reports, and adding post-build actions to publish them. Jenkins will generate visual summaries that provide insights into test performance and coverage.

## **性能测试指标(best practices)** 
1. Response time(from send to receive)
2. Throughput(number of requests within a specific time frame)
3. Concurrent users(active users/sessions same time)
4. Error rate
5. Resource Utilization(hardware resources being used)

## **测试指标**
1. Test coverage: the precentage of code or functionality covered. all critical paths and use cases are covered, new features or changes are tested.
2. Defect Density: how many bugs or issues are found, campare against previous releases or industry standards.
3. Test execution metrics: number of test cases passed, failed, or blocked. majority of test cases are executed and passed, failed are fixed, blocked are documented and has a resolution.
4. Defect leakage and resolution time: no critical or high-priority issues left, end-users acknowledge of the exsiting issues, and there will be a resolution for each issue.

## **交付指标**
1. on-time delivery
2. quality of delivery
3. number of defects after release goes alive
4. cost

## **处理未通过测试**
1. Analyze failure logs, understand reason 
2. Try to find root cause: flaky test, examine test data, debug test script, test case steps, environment issue
3. Log the issue, prioritize the fix
4. Rerun the test document resolution

## **测试计划**
1. Define test plan objectives, identify test scope
2. Determine test criteria, test strategy, test resources
3. Establish test schedule, specify test deliverables
4. Design test cases, define test environments
5. Risk management, review and update plan

## **REST和SOAP区别** <br/>
Comparing SOAP vs REST API, SOAP only works with XML formats whereas REST work with plain text, XML, HTML and JSON.
SOAP requires more bandwidth for its usage. Since SOAP Messages contain a lot of information inside of it.

## **什么是测试环境** <br/>
A test environment is a setup or configuration where software applications are tested to ensure they function correctly before being deployed to a production environment. 
It includes the hardware, software, network, databases, configurations, and any other system elements necessary to replicate the conditions under which the application will run in production.
