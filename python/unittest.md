In Python, there are several tools to help you write, organize, run, and automate your unit test. In the Python [standard library](https://docs.python.org/3/library/index.html), you’ll find two of these tools:

1. `doctest`
2. `unittest`

The `unittest` [package](https://realpython.com/python-modules-packages/#python-packages) is also a testing framework. However, it provides a more complete solution than `doctest`. In the following sections, you’ll learn and work with [`unittest`](https://docs.python.org/3/library/unittest.html#module-unittest) to create suitable unit tests for your Python code.

The framework uses an [object-oriented](https://realpython.com/python3-object-oriented-programming/) approach and supports some essential concepts that facilitate test creation, organization, preparation, and automation:

- **Test case**: An individual unit of testing. It examines the output for a given input set.
- **Test suite**: A collection of test cases, test suites, or both. They’re grouped and executed as a whole.
- **Test fixture**: A group of actions required to set up an environment for testing. It also includes the teardown processes after the tests run.
- **Test runner**: A component that handles the execution of tests and communicates the results to the user.

## Organizing Your Tests With the `TestCase` Class[](https://realpython.com/python-unittest/#organizing-your-tests-with-the-testcase-class "Permanent link")

The `unittest` package defines the `TestCase` class, which is primarily designed for writing unit tests. To start writing your test cases, you just need to import the class and subclass it. Then, you’ll add methods whose names should begin with `test`. These methods will test a given unit of code using different inputs and check for the expected results.

Here’s a quick test case that tests the built-in [`abs()`](https://realpython.com/python-absolute-value/) function:

```python
import unittest

class TestAbsFunction(unittest.TestCase):
    def test_positive_number(self):
        self.assertEqual(abs(10), 10)

    def test_negative_number(self):
        self.assertEqual(abs(-10), 10)

    def test_zero(self):
        self.assertEqual(abs(0), 0)
```

The `abs()` function takes a number as an argument and returns its absolute value. In this **test case**, you have three **test methods**. Each method checks for a specific input and output combination.

```python
import unittest

def categorize_by_age(age):
    if 0 <= age <= 9:
        return "Child"
    elif 9 < age <= 18:
        return "Adolescent"
    elif 18 < age <= 65:
        return "Adult"
    elif 65 < age <= 150:
        return "Golden age"
    else:
        return f"Invalid age: {age}"
        
class TestCategorizeByAge(unittest.TestCase):
    def test_child(self):
        self.assertEqual(categorize_by_age(5), "Child")

    def test_adolescent(self):
        self.assertEqual(categorize_by_age(15), "Adolescent")

    def test_adult(self):
        self.assertEqual(categorize_by_age(30), "Adult")

    def test_golden_age(self):
        self.assertEqual(categorize_by_age(70), "Golden age")

    def test_negative_age(self):
        self.assertEqual(categorize_by_age(-1), "Invalid age: -1")

    def test_too_old(self):
        self.assertEqual(categorize_by_age(151), "Invalid age: 151")
        
    def test_boundary_child_adolescent(self):
        self.assertEqual(categorize_by_age(9), "Child")
        self.assertEqual(categorize_by_age(10), "Adolescent")

    def test_boundary_adolescent_adult(self):
        self.assertEqual(categorize_by_age(18), "Adolescent")
        self.assertEqual(categorize_by_age(19), "Adult")

    def test_boundary_adult_golden_age(self):
        self.assertEqual(categorize_by_age(65), "Adult")
        self.assertEqual(categorize_by_age(66), "Golden age")
```

don't forget to read about [[https://realpython.com/python-json/|`setUp()`]] and [[https://realpython.com/python-json/|`setUpModules()`]].