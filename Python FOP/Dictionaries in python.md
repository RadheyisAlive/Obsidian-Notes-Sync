In Python, a **dictionary** is a collection of key-value pairs. Each key is associated with a value, and you can access the value by referencing the key. Dictionaries are mutable, meaning you can change them after they're created, and they are defined using curly braces `{}`.

Here is a simple example to explain:

```Python
python
Copy code
# Creating a dictionary
person = {
    "name": "John",
    "age": 30,
    "city": "New York"
}

# Accessing a value using a key
print(person["name"])  # Output: John

# Adding a new key-value pair
person["job"] = "Engineer"

# Updating an existing value
person["age"] = 31

# Deleting a key-value pair
del person["city"]

# Printing the updated dictionary
print(person)

```

### Explanation:

1. **Creating a dictionary**: We define a dictionary called `person` with three key-value pairs: `"name"`, `"age"`, and `"city"`.
2. **Accessing a value**: To get the value associated with a key, we use `person["name"]`, which gives `"John"`.
3. **Adding a key-value pair**: We add `"job": "Engineer"` to the dictionary.
4. **Updating a value**: We update the `"age"` to `31`.
5. **Deleting a key-value pair**: We remove the `"city"` key from the dictionary using the `del` keyword.

Final output after all operations will be:

```Python
python
Copy code
{'name': 'John', 'age': 31, 'job': 'Engineer'}

```

Dictionaries are very useful for storing data in a structured way where you can quickly look up values based on unique keys.