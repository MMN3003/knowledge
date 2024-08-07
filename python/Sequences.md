`Lists`, `tuples`, and `strings` are among Python’s most basic data types. Even though they’re different types with distinct characteristics, they have some common traits. You can summarize the characteristics that define a Python sequence as follows:

- A sequence is an [iterable](https://realpython.com/python-iterators-iterables/), which means you can iterate through it.
- A sequence has a length, which means you can pass it to [`len()`](https://realpython.com/len-python-function/) to get its number of elements.
- An element of a sequence can be accessed based on its position in the sequence using an integer index. You can use the square bracket notation to index a sequence.
```python
# List
countries = ["USA", "Canada", "UK", "Norway", "Malta", "India"]
for country in countries:
    print(country)

# USA
# Canada
# UK
# Norway
# Malta
# India
len(countries)
# 6
countries[0]
# 'USA'

# Tuple
countries = "USA", "Canada", "UK", "Norway", "Malta", "India"
for country in countries:
    print(country)

# USA
# Canada
# UK
# Norway
# Malta
# India
len(countries)
# 6
countries[0]
'USA'

# Strings
country = "India"
for letter in country:
    print(letter)
# I
# n
# d
# i
# a
len(country)
# 5
country[0]
# 'I'
```

There are other built-in data types in Python that also have all of these characteristics. One of these is the [`range` object](https://realpython.com/python-range/):
```python
numbers = range(5, 11)
type(numbers)
# <class 'range'>

len(numbers)
# 6

numbers[0]
# 5
numbers[-1]
# 10

for number in numbers:
    print(number)

# 5
# 6
# 7
# 8
# 9
# 10
```
# `Sequences` Methods
In Python, the key characteristics of a data type are determined using [special methods](https://realpython.com/python-magic-methods/), which are defined in the class definitions. The special methods associated with the properties of sequences are the following:

- **`.__iter__()`**: This special method makes an object iterable using Python’s preferred iteration protocol. However, it’s possible for a class without an `.__iter__()` special method to create iterable objects if the class has a `.__getitem__()` special method that supports iteration. Most sequences have an `.__iter__()` special method, but it’s possible to have a sequence without this method.
- **`.__len__()`**: This special method defines the length of an object, which is normally the number of elements contained within it. The `len()` built-in function calls an object’s `.__len__()` special method. Every sequence has this special method.
- **`.__getitem__()`**: This special method enables you to access an item from a sequence. The square brackets notation can be used to fetch an item. The expression `countries[0]` is equivalent to `countries.__getitem__(0)`. For sequences, `.__getitem__()` should accept integer arguments starting from zero. Every sequence has this special method. This method can also ensure an object is iterable if the `.__iter__()` special method is missing.
# Slicing in Python Sequences[](https://realpython.com/python-sequences/#slicing-in-python-sequences "Permanent link")
```python
countries = ["USA", "Canada", "UK", "Norway", "Malta", "India"]
countries[1:4]
# ['Canada', 'UK', 'Norway']

countries = "USA", "Canada", "UK", "Norway", "Malta", "India"
countries[1:4]
# ('Canada', 'UK', 'Norway')

country = "India"
country[1:4]
# 'ndi'

numbers = range(5, 11)
numbers[1:4]
# range(6, 9)
```
# Concatenating `Sequences`
```python
[1, 2, 3] + [4, 5, 6]
# [1, 2, 3, 4, 5, 6]

(1, 2, 3) + (4, 5, 6)
# (1, 2, 3, 4, 5, 6)

[1, 2, 3] + (4, 5, 6)
# Traceback (most recent call last):
# TypeError: can only concatenate list (not "tuple") to list
```
# `id()` `Sequences`
The extended list is the same object as the original `numbers_list`. The value returned by the built-in `id()` function is the same before and after the augmented assignment operation. However, the behavior is different when using tuples:
```python
# list
numbers_list = [1, 2, 3]
id(numbers_list)
# 4331793920
numbers_list += [4, 5, 6]
numbers_list
# [1, 2, 3, 4, 5, 6]
id(numbers_list)
# 4331793920


# tuple
numbers_tuple = 1, 2, 3
id(numbers_tuple)
# 4331564032
numbers_tuple += 4, 5, 6
numbers_tuple
# (1, 2, 3, 4, 5, 6)
# This is a new tuple object
id(numbers_tuple)
4331414688
```

# Comparing Values With Sequences
```python
countries_list = ["USA", "Canada", "UK", "Norway", "Malta", "India"]
countries_tuple = "USA", "Canada", "UK", "Norway", "Malta", "India"

countries_list == countries_tuple
# False
countries_list == countries_list
# True

numbers = [1, 2, 3, 4, 5]
more_numbers = [1, 2, 2, 10, 20]

numbers > more_numbers
# True

numbers = [1, 2, 3]
more_numbers = [1, 2]
numbers > more_numbers
# True

numbers = [1, 0, 3]
numbers > more_numbers
# False
```
Both lists have the same first two values. However, the third item in `numbers` is larger than the third item in `more_numbers`. Therefore, `numbers` is greater than `more_numbers` even though the remaining integers in `more_numbers` are larger.

# Creating User-Defined Python Sequences
```python
class ShapePoints:
    def __init__(self, points):
        self.points = list(points)
```