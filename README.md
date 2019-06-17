# qvalidation

Simple data validation for python

## Rules
- required

## Basic Usage:
```
from qvalidation import Validation, rule

v = Validation() # or v = Validation(data)

v.set_data({'name': 'John', 'age': '19'})

v.set_rule(field='name', label='Name', rule=rule.required)
v.set_rule('age', 'Age', lambda value: value > 20, message='{label} should be greater then 20')

if not v.is_valid(True):
    print(v.errors)

if v.is_invalid(True):
    print(v.errors) # {'name': 'Name is required', 'age'}

print(v.errors(True)) # return {} if valid

```

# Runing Tests

In root folder
```
$ python -m unittest
```
