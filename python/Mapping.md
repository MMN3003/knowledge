# defauldict
1. create default for `dict` by `defaultdict` of `collections` package.
``` python
from collections import defaultdict

points = {
     "Denise": 3,
     "Igor": 2,
     "Sarah": 3,
     "Trevor": 1,
 }
points["Sarah"]
# 3
 points["Matt"]
# Traceback (most recent call last):
# KeyError: 'Matt'

# set a default for non-existing key
points_default = defaultdict(
   lambda: 0,
   points,
)
points_default
#defaultdict(<function <lambda> at 0x104a95da0>, {'Denise': 3,'Igor': 2, 'Sarah': 3, 'Trevor': 1})
points_default["Sarah"]
# 3
points_default["Matt"]
# 0
points_default
#defaultdict(<function <lambda> at 0x103e6c700>, {'Denise': 3,'Igor': 2, 'Sarah': 3, 'Trevor': 1, 'Matt': 0})

```
# counter
2. calculate letter reputation in string by `counter` of `collections` package.[[Mapping#keys,values,items]]
``` python
from collections import Counter
letters = Counter("learning python")
letters
#Counter({'n': 3, 'l': 1, 'e': 1, 'a': 1, 'r': 1, 'i': 1, 'g': 1,' ': 1, 'p': 1, 'y': 1, 't': 1, 'h': 1, 'o': 1})

letters.keys() 
# dict_keys(['l', 'e', 'a', 'r', 'n', 'i', 'g', ' ', 'p', 'y', 't','h', 'o'])

letters.values()
# dict_values([1, 1, 1, 1, 3, 1, 1, 1, 1, 1, 1, 1, 1])

letters.items()
# dict_items([('l', 1), ('e', 1), ('a', 1), ('r', 1), ('n', 3),('i', ),('g', 1), (' ', 1), ('p', 1), ('y', 1), ('t', 1),('h', 1), ('o', 1)])
```
# keys,values,items
3. `keys()`, `values()` and `items()` of `dict`.The `dict_keys`, `dict_values`, and `dict_items` objects are [dictionary views](https://docs.python.org/3/glossary.html#term-dictionary-view). These objects do not contain their own data, but they provide a view of the data stored within the mapping. To experiment with this idea, you can assign one of the views to a variable and then change the data in the original mapping.
```python
points.keys()
# dict_keys(['Denise', 'Igor', 'Sarah', 'Trevor'])

points.values()
# dict_values([3, 2, 3, 1])

points.items()
# dict_items([('Denise', 3), ('Igor', 2), ('Sarah', 3), ('Trevor', 1)])

for name, number in points.items():
     print(f"Number of points for {name}: {number}")

# Number of points for Denise: 3
# Number of points for Igor: 2
# Number of points for Sarah: 3
# Number of points for Trevor: 1

values_in_points = points.values()
values_in_points
# dict_values([3, 2, 3, 1])

points["Igor"] += 10

values_in_points
# dict_values([3, 12, 3, 1])
```
# `Mapping`, `MutableMapping`
4.  `Mapping` and `MutableMapping` abstract class in `collection.abc` package.
```python
from collections import Counter
from collections.abc import Mapping, MutableMapping
points = {
    "Denise": 3,
	"Igor": 2,
    "Sarah": 3,
    "Trevor": 1,
}

isinstance(points, Mapping)
# True
isinstance(points, MutableMapping)
# True

letters = Counter("learning python")
isinstance(letters, MutableMapping)
# True

```
## `Mapping` Methods
The _required_ special methods you need to define when you create a **`Mapping`** are the following:

- **`.__getitem__()`**: Defines how to access values using the square brackets notation.
- **`.__iter__()`**: Defines how to iterate through the mapping.
- **`.__len__()`**: Defines the size of the mapping.

The `Mapping` abstract base class also provides the following methods:

- **`.__contains__`**: Defines how to determine membership of the mapping.
- **`.__eq__()`**: Defines how to determine equality of two objects.
- **`.__ne__()`**: Defines how to determine when two objects are not equal.
- **`.keys()`**: Defines how to access the keys in the mapping.
- **`.values()`**: Defines how to access the values in the mapping.
- **`.items()`**: Defines how to access the key-value pairs in the mapping.
- **`.get()`**: Defines an alternative way to access values using keys. This method allows you to set a default value to use if the key isn’t present in the mapping.
```python
from collections.abc import Mapping

class PizzaMenu(Mapping):
    def __init__(self, menu: dict):
        self._menu = menu

    def __getitem__(self, key):
        return self._menu[key]

    def __iter__(self):
        return iter(self._menu)

    def __len__(self):
        return len(self._menu)
        
	def __repr__(self):
        return f"{self.__class__.__name__}({self._menu})"
        
    def __str__(self):
        return str(self._menu)

menu = PizzaMenu({"Margherita": 9.5, "Pepperoni": 10.5})
menu
# {'Margherita': 9.5, 'Pepperoni': 10.5}
```
## `MutableMapping` Methods
`MutableMapping` inherits from `Mapping`. Therefore, it includes all the methods present in [[Mapping#`Mapping` Methods|`Mapping`]], but has two additional required special methods:

- **`.__setitem__()`**: Defines how to set a new value for a key.
- **`.__delitem__()`**: Defines how to delete an item in the mapping.

The `MutableMapping` abstract base class also adds these methods:

- **`.pop()`**: Defines how to remove a key from a mapping and return its value.
- **`.popitem()`**: Defines how to remove and return the most recently added item in a mapping.
- **`.clear()`**: Defines how to remove all the items from the mapping.
- **`.update()`**: Defines how to update a dictionary using data passed as an argument to this method.
- **`.setdefault()`**: Defines how to add a key with a default value if the key isn’t already in the mapping.