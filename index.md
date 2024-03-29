---
marp: true
theme: gaia
size: 4K
class: default
paginate: true
footer: @asm0di0 &emsp13;&emsp13;@if_no_then_yes
backgroundImage: "linear-gradient(to bottom, #000 0%, #1a2028 50%, #293845 100%)"
color: white
title: "Testing Data Pipelines: Himalayan peaks"
---
<!--
_class: lead
_paginate: false
_footer: ""
-->

<style>
footer {
    display: table
}
.hljs-variable { color: lightblue }
.hljs-string { color: lightgreen }
.hljs-params { color: lightpink }
</style>

# Himalayan Peaks
## of Testing Data Pipelines

Ksenia Tomak, HelloFresh
Pasha Finkelshteyn, JetBrains

---

<!-- _class: lead -->
# Pasha Finkelshteyn

![bg brightness:40%](images/asm0dey.jpg)

Developer :avocado: for Big Data @ JetBrains

@asm0di0

:elephant: @asm0dey@fosstodon.org

---

<!-- _class: lead -->
# Data processing

![width:700](images/etl.png)

---
<!-- _backgroundImage: "linear-gradient(to bottom, #000, #000)" -->

# Data lake?

![width:1140](images/datalake_layers.jpg)

---

# Who needs pipelines

- Data Scientists
- Data Analytics
- Marketing
- PO

---

<!-- _class: lead -->
# <!-- fit --> It have to be tested!

---
<!-- _class: lead -->
# Pyramid of testing?


---
<!-- _class: lead -->
# Pyramid of testing?

![bg right:57% fit brightness:0.9](images/pyramid_e.png)

---

![bg fit](images/real_pyramid.webp)

---

# Pyramid of testing. Unit

![bg](images/unit.png)

---

<!-- _backgroundImage: "linear-gradient(to bottom, #000, #000)" -->

# Bronze→Silver pipeline

![width:1140](images/datalake_bronze.jpg)

---

# Typical pipeline

![bg](images/pipeline.png)

---
# Typical pipeline

![width:1000](images/spark-j1.svg)

---
# Typical pipeline

![width:1000](images/spark-j2.svg)

---
# Typical pipeline

![width:1000](images/spark-j3.svg)

---
# Typical pipeline

![width:1000](images/spark-j4.svg)

---
# Typical pipeline

![width:1000](images/spark-j5.svg)

---

# Unit testing of pipeline

What may we test here?

A pipeline should transform data correctly!

_Correctness is a business term_

---

# Let's paste fakes!

![bg](images/unit_pipeline.png)

Fake input data
Reference data at the end of the pipeline

---

# Tools

[holdenk/spark-testing-base](https://github.com/holdenk/spark-testing-base) ← Tools to run tests
[MrPowers/spark-daria](https://github.com/MrPowers/spark-daria) ← tools to easily create test data

---

# Component testing

![bg](images/component.png)

---

![bg](https://d33wubrfki0l68.cloudfront.net/a661dbbe55be3e9cb77889f24835a44c6daf53c2/ce0aa/logo.png)

---

# TestContainers

![bg](images/docker_pipeline.png)


---

# TestContainers

Supported languages:

- Java (and compatibles: Scala, Kotlin, etc.)
- Python
- Go
- Node.js
- Rust
- .NET

---

# Test Containers
![width:1140](images/tc-python1.png)

---

# Test Containers
![width:1140](images/tc-python2.png)

---

# Test Containers
![width:1140](images/tc-python3.png)

---

![bg](images/systems.png)

---

<!-- _backgroundImage: #FFFFFF -->
<!-- _backgroundColor: "rgb(255,255,255)" -->
![](images/enterprise-bi-adf.png)

---
# Real systems

Why are component tests not enough?

- vendor lock tools (DB, processing, etc.)
- external error handling

---

![bg](images/data.png)

---

![bg 110%](images/sample.png)

# Real data
<br/>

Get data samples from prod, 
anonymize it

---

# Compare to reference

![bg 89%](images/reference.png)

---

# Comparison example

gender | reference | id | match
:-----:|:---------:|---:|-----:
  m    | m         | 1  | TRUE
  f    | c         | 2  | FALSE
  u    | u         | 3  | TRUE
  c    | c         | 4  | TRUE
  m    | f         | 5  | FALSE


---
<!-- _class: lead -->

# Real data

Deploy full data backup on stage env, anonymize it :money_mouth_face:

---

<!-- _class: lead -->
# <!-- fit --> In usual testing you won't trust your code

---
<!-- _class: lead -->

# <!-- fit --> In pipeline testing  you won't trust 
# <!-- fit --> both your code and your data

---
# Real data expectations
Test:
✅ no data
✅ valid data
❓ invalid data
❓ illegal data format

---

# Real data expectations. Tools: 
- [great expectations](https://greatexpectations.io/),
- [Deequ](https://github.com/awslabs/deequ)

<!-- 
_footer: '[Automated Testing For Protecting Data Pipelines from Undocumented Assumptions
](https://databricks.com/session_na20/automated-testing-for-protecting-data-pipelines-from-undocumented-assumptions)'
-->

---

## Real data expectations

- profilers
- constraint suggestions
- constraint verification
- metrics
- metrics strores
---

![width:1140](images/dq1.svg)

---

![width:1140](images/dq2.svg)

---

![width:1140](images/dq3.svg)

---

![width:1140](images/dq4.svg)

---
## Great expectations

![width:1140](images/ge-1.svg)

---

<style scoped>
p > img {
    display:block;
    margin:auto;
}
</style>

## Great expectations
![height:480](images/ge_result.svg)

---
## Python Deequ

![width:1140](images/pydq1.png)


<!-- 
_footer: '
[Testing data quality at scale with PyDeequ
](https://aws.amazon.com/blogs/big-data/testing-data-quality-at-scale-with-pydeequ/)

[PyDeequ documentation](https://pydeequ.readthedocs.io/_/downloads/en/latest/pdf/)'
-->

---
## Python Deequ

![width:1140](images/pydq2.png)


<!-- 
_footer: '
[Testing data quality at scale with PyDeequ
](https://aws.amazon.com/blogs/big-data/testing-data-quality-at-scale-with-pydeequ/)

[PyDeequ documentation](https://pydeequ.readthedocs.io/_/downloads/en/latest/pdf/)'
-->

---
## Python Deequ

![width:1140](images/pydq3.png)


<!-- 
_footer: '
[Testing data quality at scale with PyDeequ
](https://aws.amazon.com/blogs/big-data/testing-data-quality-at-scale-with-pydeequ/)

[PyDeequ documentation](https://pydeequ.readthedocs.io/_/downloads/en/latest/pdf/)'
-->

---
## Python Deequ

![width:1140](images/pydq4.png)


<!-- 
_footer: '
[Testing data quality at scale with PyDeequ
](https://aws.amazon.com/blogs/big-data/testing-data-quality-at-scale-with-pydeequ/)

[PyDeequ documentation](https://pydeequ.readthedocs.io/_/downloads/en/latest/pdf/)'
-->

---
## Python Deequ.

constraint | constraint_status | constraint_message
-----|------|:-----:
CompletenessConstraint | Success |  
ComplianceConstraint | Failure | Value: 0.5 does not meet the constraint requirement!

---
## Real data ecpectations. Use cases

* pre-ingestion and post-ingestion data validaton
* before pipeline development
* monitoring and alerting

---

![bg](images/monitoring.png)

---

# Monitoring 

**Why?**

- The only REAL testing is production
- Data tends to change over time

---

# Monitoring 

What?
* data volumes
* counters
* time
* dead letter queue monitoring
* service health
* business metrics

---

# Monitoring 

How?
- use Listeners
- use data aggregations
- AirFlow (or another orchestrator)

---
<!-- _class: lead -->
# Data pipelines is always DAG
Monitoring should visualize it
<!-- Specifics of data pipeline monitoring -->

---

<!-- 
_color: black
_backgroundImage: "linear-gradient(to bottom, #fff 0%, #fff 100%)"
_footer: '[Visualizing Data Timeliness](https://medium.com/airbnb-engineering/visualizing-data-timeliness-at-airbnb-ee638fdf4710)'
-->

### Monitoring visualization

![bg fit](images/visualize.png)

---
# End-to-End tests

Compare with reports, old DWH

Multiple dimensions:
- data
- data latency
- performance, scalability

---

![bg](images/performance.png)

---

# Performance Tests

<br/>
<br/>
<br/>
<br/>

- start with SLO
- test your initial data load

![bg](images/initial.png)

---

# Real prod

<br/>
Run a parallel job with a different sink

![bg](images/parallel.png)

<!--_footer: '@asm0di0 &emsp13;&emsp13;@if_no_then_yes

[Using production data for testing in a post GDPR world](https://www.sqlshack.com/using-production-data-testing-post-gdpr-world/)'-->

---

![bg fit](images/final_pyramid.png)

---

# Summary

* Testing pipeline is like testing code
* Testing pipelines is not like testing code
* Pipeline quality is not only about testing
* Sometimes testing outside of production is tricky

---

<!-- 
_class: lead
_footer: ""
 -->

# Thanks!
## Questions? :bow:

@asm0di0
@if_no_then_yes

:elephant: @asm0dey@fosstodon.org
