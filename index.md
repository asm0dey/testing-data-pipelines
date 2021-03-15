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

# Testing Data Pipelines
## Himalayan peaks

Ksenia Tomak, Dodo Engineering
Pasha Finkelshteyn, JetBrains

---

# Who we are

---

# What is Big Data

---

# Who are DEs?

---

# What is pipeline?

---

# Who needs pipelines

---

# QA of pipeline

QA ?= QC

---

# QA of pipeline

QA ≠ QC

QA is about processes, and not only about software quality.

---

# Pyramid of testing. Unit

...pic of unit trapezium here...

---

# Typical pipeline

...pic with one source and one target...

---

# Unit testing of pipeline

What may we test here?

A pipeline should transform data correctly!

_Correctness is a business term_

---

# Let's paste fakes!

...pic of the pipeline with fake input...

Fake/mock input data
Reference data at the end of pipeline

---

# Component testing

...pic of augmented pyramid with components...

---

![bg](https://d33wubrfki0l68.cloudfront.net/a661dbbe55be3e9cb77889f24835a44c6daf53c2/ce0aa/logo.png)

---

# Test Containers

```python
import sqlalchemy
from testcontainers.mysql import MySqlContainer

with MySqlContainer('mysql:5.7.17') as mysql:
    engine = sqlalchemy.create_engine(mysql.get_connection_url())
    version, = engine.execute("select version()").fetchone()
    print(version)  # 5.7.17
```

---

# TestContainers

Supported languages:

* Java (and compatibles: Scala, Kotlin, etc.)
* Python
* Go
* Node.js
* Rust
* .NET

---

# TestContainers

...pic of pipeline with docker as source...