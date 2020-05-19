---
title: "Python: list comprehension"
date: 2020-03-16
draft: false
categories:
  - kursy
  - Python
tags:
  - python
  - coursera
---

### cała lista

new_list = [element.method() for element in old_list]

### wrunkowo z if

new_list = [element.method() for element in old_list if element = "chosen"]

### warunkowo z if/else

new_list = [element.method() if element != "exception" else element.exception_method() for element in old_list]
