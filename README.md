📌 Introduction

Apache JMeter is an open-source tool developed by the Apache Software Foundation. It is primarily used for performance and load testing of web applications by simulating concurrent users and analyzing response behavior.

🧪 0. Types of Performance Testing

Type

Description

Load Testing

Evaluating system performance under expected user load.

Stress Testing

Pushing the system beyond its capacity to identify its breaking point.

Endurance Testing

Also known as Soak Testing; checking if the system can handle prolonged load.

Spike Testing

Sudden increase in user load to analyze system behavior.

Volume Testing

Assessing system behavior with a massive amount of input data.

🧱 1. What is JMeter?

Free, open-source performance testing tool.

Supports various protocols: HTTP, HTTPS, SOAP, REST, FTP, JDBC, etc.

Capable of testing web apps, databases, APIs, and more.

⚙️ 2. Setting Up a Test Scenario

Basic Steps:

Launch JMeter GUI

Create a Test Plan

Add a Thread Group (users, loops, ramp-up)

Add an HTTP Request sampler

Add Listeners such as View Results Tree, Summary Report

Add CSV Data Set Config for dynamic test data

Add Assertions to validate the response

JMeter Components:

Thread Group: Simulates user threads

Samplers: HTTP Request, JDBC Request, etc.

Config Elements: CSV Data Set Config, HTTP Header Manager

Assertions: Validate correctness of responses

Listeners: Display and analyze test results

Timers: Add delay between requests

Logic Controllers: Conditional flow (Loop, If, Switch)

Test Fragments: Reusable module structures

🧪 3. Adding Assertions in JMeter

Steps to Add Response Assertion:

Right-click on HTTP Request → Add → Assertions → Response Assertion

Set "Field to Test": Response Body / Code / Headers / etc.

Select "Pattern Matching Rule": Contains / Equals / Matches / Substring

Add expected value under "Patterns to Test"

Common Assertions:

Type

Function

Response Assertion

Validate text or value in the response body

Duration Assertion

Ensure response time is within acceptable limit (in ms)

Size Assertion

Validate response size (bytes)

JSON Assertion

Check structure and value in JSON responses

XML Assertion

Check presence of specific XML nodes or content

📌 4. Using Parameters and Dynamic Data

Dynamic data can be referenced using ${parameterName}.

Example URL:

/web/index.php/pim/viewPersonalDetails/empNumber/${ID}

To configure dynamic IDs:

Add CSV Data Set Config to the Thread Group:

Filename: users.csv

Variable names: ID

Delimiter: ,

Recycle on EOF: true

Stop thread on EOF: false

🛠 5. Recording with HTTP(S) Test Script Recorder

Record user actions in the browser using JMeter as a proxy.

Browser configuration must include the JMeter certificate.

Alternate options:

Export HTTP requests from Postman

Manually replicate requests using browser DevTools (copy as cURL)

⚠️ 6. Common Errors and Troubleshooting

Error Message

Cause

ModuleController: has no selected Controller

No controller selected in Module Controller.

URISyntaxException

Illegal characters (e.g. \, %20) in URL

Non HTTP response code

Server unreachable, invalid domain, or network issue

📊 7. Analyzing Test Results

Key Metrics:

Load Time: Time taken to get full response

Connect Time: Time taken to establish TCP connection

Latency: Time until first byte received

Throughput: Requests per second

Error %: Error rate of requests

90% Line: 90% of samples responded faster than this value

Useful Listeners:

Summary Report

Aggregate Report

View Results Tree

Graph Results

✅ 8. Performance Evaluation and Decision Making

Steps:

Monitor Throughput and Error Rate for overall health

Use Assertions to ensure response validity

Check Latency and Connect Time for delays

Analyze server-side metrics (CPU, RAM, DB connections)

Run tests in different environments (Dev, QA, Prod)

Gradually increase load: 10 → 50 → 100+ users

Identify bottlenecks: database, app server, network

🧰 9. Tools and Enhancements

JMeter Plugins Manager:

Ultimate Thread Group

Custom Graphs

Backend Listener (for Grafana)

Grafana + InfluxDB for real-time dashboards

Excel or Google Sheets for offline analysis

🌐 10. Useful Resources

Official Website: https://jmeter.apache.org

Dummy API: https://dummyjson.com/docs/products

Test App: https://opensource-demo.orangehrmlive.com
