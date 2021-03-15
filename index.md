---
marp: true
theme: gaia
size: 4K
class: default
paginate: true
footer: @asm0di0 &emsp13;&emsp13;@if_no_then_yes
backgroundImage: "linear-gradient(to bottom, #000 0%, #1a2028 50%, #293845 100%)"
color: white
title: Noname
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

# Testing data pipeines

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

# Emulating real systems

