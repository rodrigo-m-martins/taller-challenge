# taller-challenge

TODO: Create a Github repo for delivery md files.


Challenge (30–45 min): Unified Mini Automation Framework Design Objective 
Evaluate your ability to design the architecture of a unified framework for Mobile + API + Web  automation, without going into excessive detail. 
No coding is required. 
Deliverable: A file named framework_overview.md 
1. High-Level Architecture (5 minutes) 
Describe only the overall structure, for example: 
Modules: api/, mobile/, web/, core/ 
I would create a core/root/base structure that could share some base structure like some containers that allow emulate local environment for test linked to the latest versions published from dev to all modules, considering a standard adopted in the project.
To the API, MOBILE and WEB, I would reuse the base structure adding what is necessary
In separate I would create modules specialized to implement validation for business rules and then reuse it widely where necessary.
In the end the data repository should be used to handle the reporting of those test results, with the relative bias to the interested in receive it
What should be included in core/ (config, drivers, logger, utils)
In the core/root module , would set things commonly reused and base configs that can be required from each module, like creation of data, external access to resources like cloud services and other related external dependencies.
But to be explicit, would not set validations(business rules) into core module because it can increase too much the complexity.
Whether you would use a Gradle multi-module setup or a single repository, and why.
It depends on the amount of code that should be created and the complexity to perform rules validation
 Goal: Assess your understanding of modularity. 
2. API Testing (Kotlin + RestAssured / Ktor / OkHttp) – 5 minutes 
Explain only: 
How you would model requests/responses 
Apply Open API and W3C standards
The HTTP methods
Json schema
How you would reuse a shared API client
Having the data as key to have a result verified at the end of request  by the input used (Data Driven).
How you would handle environments (e.g., env.yaml file)
Depending on the solution it can also be a xml file or a vault/secret manager. 
Goal: Validate scalable design—not focus on specific tools. 
3. Web UI Automation (Selenium or Cypress) – 5 minutes 
Briefly indicate: 
Use of the Page Object Model 
Make easy to maintain tests over web applications
Handling of waits 
Avoid spend time and computational resources
Local vs. remote execution (Selenium Grid) 
Depends on the current moment. But for scheduled executions, remote, for debug and improvements, local.
Goal: Evaluate understanding of test stability.
4. Mobile Automation (Kotlin + Appium) – 5 minutes Explain only: 
Structure based on a Screen Object Model 
Map elements relevant to the usage during interaction required to perform an necessary action.
Increase performance of test execution
How capabilities would be managed
Depending on which platform should be used to the test, it can be set in the driver initialization
Parallel execution on 2–3 simulated devices 
Having this availability is the ideal scenario but not so common. Prioritize different versions of OS and a baseline SDK from application development. .
Check if there is some transient dependency issue.
Goal: Detect real Appium experience. 
5. Configuration, Execution, and Environments – 5 minutes Describe: 
A single configuration file (config.yaml)
It's an “easy to read” way to document, manage and describe settings widely used by modern developers.
How to pass environment parameters (e.g., --env=staging)
Considering springboot there are some settings that can be passed with this sintaxe but not the only way. Can be set into environment variables and be set from files like pom.xml(maven) or by gradle build framework.
 How to separate executions by suite: api, web, mobile Goal: Confirm understanding of configuration best practices. 
6. CI/CD (Simple Pipeline) – 5 minutes 
Explain: 
How suites run in a pipeline
Suites can be parametrized to set a environment and perform test over a version that the own framework can build, deploy and handle tests depending on the needs.
Use of matrix execution (API + Web + Mobile in parallel) 
It allow have easy scheduling to fixes related to validate new and/or dynamic business rules bug fixes and releases in a agile way)
Which reporter you would use (Allure / JUnit XML)
I’ve used TestNG more frequently. But it’s only a tool, not an issue to pick a different one .
 Goal: Assess real pipeline experience. 
7. Mini-Diagram (Optional, 2 minutes) 
A very simple structure, e.g.: 
/framework 
/core 
/api 
/web 
/mobile
