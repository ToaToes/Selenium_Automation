# Selenium_Automation
Selenium Automation DevOps, involing repository Gitlab, Jenkins CI Line (or docker), Jenkins automation (UI, API(Postman)), then end product.


The CI/CD pipeline is a set of automated processes that allow development teams to integrate  ```code changes```, ```run tests```, and ```deploy applications``` more efficiently. breakdown of the typical process and how the various components like:
**GitLab**, 
**Jenkins**, 
**server backend**, 
**Postman**,
**UI automation,** 
**API testing**
interact within this pipeline:

CI/CD Pipeline Process
Code Commit:

Developers push code changes to a version control system (e.g., GitLab). This can include new features, bug fixes, or configuration changes.
Continuous Integration (CI):

Trigger: A commit to the repository triggers the CI process in Jenkins.
Build: Jenkins pulls the latest code from the GitLab repository and compiles/builds the application.
Testing: Jenkins runs automated tests (including unit tests, integration tests, API tests, etc.). This can involve:
API Testing: Using tools like Postman or Newman to run predefined API tests against the latest build.
UI Automation: Running automated UI tests to verify the user interface and user experience.
Continuous Deployment (CD):

If all tests pass, Jenkins automatically deploys the application to a staging or production server.
This could involve pushing code to the backend server where the application runs.
Monitoring and Feedback:

After deployment, the application is monitored for performance and errors. Feedback from users can also be collected for further improvements.
Iteration:

Developers receive feedback and continue to make improvements or fix issues, starting the process again.
Relationships Between Components
GitLab Repository:

Acts as the source control where the product's codebase resides. Changes made by developers are pushed here.
Jenkins:

CI/CD automation server that listens for changes in the GitLab repository. It orchestrates the build and testing process, triggering jobs based on repository events (like commits).
Server Backend:

The environment where the application is deployed. Jenkins can deploy the built application here if all tests are successful.
Postman:

Used for API testing. Postman collections can be run through Newman in Jenkins to ensure that API endpoints work as expected with the latest code.
UI Automation:

Automated tests that interact with the user interface of the application, verifying that the front end behaves correctly after changes. These tests can also be triggered by Jenkins as part of the CI/CD process.
API Testing:

Specifically focuses on validating the functionality and performance of API endpoints. This can be part of the testing phase in Jenkins, where Postman or other testing frameworks are used.
Visual Workflow
Developer pushes code → GitLab Repository
Jenkins detects the change → Triggers CI process
Jenkins pulls code, builds application, and runs tests:
API Tests (Postman/Newman)
UI Tests
If tests pass → Jenkins deploys to the server backend



## Situation that not suitable for automation:
1. Short-Lived Projects
Description: For projects with a very short lifespan or one-time applications, the time and effort needed to set up automated tests may outweigh the benefits.
2. Highly Dynamic User Interfaces
Description: Applications with frequently changing UIs may require constant updates to the test scripts, leading to maintenance overhead that can negate the benefits of automation.
3. Exploratory Testing
Description: Exploratory testing, which relies on human intuition and experience, cannot be easily automated. This type of testing is valuable for discovering unexpected issues.
4. Complex Test Scenarios
Description: Tests that involve complex user interactions, require human judgment, or depend heavily on visual aspects (like design reviews) may be challenging to automate effectively.
5. Initial Development Phases
Description: In the early stages of development, when requirements are still evolving, automation may not be suitable. The test cases can become obsolete quickly, leading to wasted effort.
6. Low ROI on Automation
Description: If the cost of setting up and maintaining automated tests is higher than the benefits gained (e.g., in small teams or projects with minimal regression testing), it may not be justified.
7. Test Cases with High Setup Costs
Description: Tests that require extensive setup, configuration, or specific environments can be cumbersome to automate and may be more efficiently executed manually.
8. Non-Functional Testing
Description: While some non-functional tests can be automated (like performance testing), others, such as usability or accessibility testing, often require human input and subjective evaluation.
9. Specialized Hardware or Devices
Description: Testing applications that rely on specific hardware configurations or devices (like IoT devices) may not be feasible to automate effectively.
Monitoring occurs post-deployment → Feedback loop starts again
Conclusion
In summary, the CI/CD pipeline integrates various tools and processes to automate the development workflow, ensuring that code changes are continuously tested and deployed efficiently. Each component plays a crucial role in maintaining the quality and stability of the software throughout its lifecycle.
