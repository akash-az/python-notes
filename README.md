# python-notes

```python

print function  : print()

print("Day 1 - Python Print Function")
print("The function is declared like this:")
print("print('what to print')")  // for printing quotes as is. using 2nd " " will give error, taking it as a part of the code.

Task : take string input from a user and print its no of characters.

Why print(len(x)) works
print() can take multiple arguments, and it automatically converts them to strings.

print(len(x)) works because print() internally calls str(len(x)) before displaying it.

Why "string" + len(x) fails
The + operator requires both operands to be of the same type (both strings or both numbers).

Since len(x) is an integer, Python raises a TypeError when trying to concatenate a string with an integer.

Correct Ways to Print Without Error
Convert len(x) to string manually

python

print("Length of string " + x + " is " + str(len(x)))
Use f-strings (best way)

python

print(f"Length of string {x} is {len(x)}")
Pass multiple arguments to print()

python

print("Length of string", x, "is", len(x))
Here, print() automatically converts everything to a string and separates them with spaces.


Exercise : Band Name Generator > take input from user of their city and pet name combine them and display them as their band name

# solution :
print("Welcome to band generator");
city_name = input("Name of the city u grew up in\n") # \n puts the cursor to the next line for input.
pet_name = input("Name of your favourite pet\n")
print(f"name of your band could be : {city_name} ke {pet_name} ")

                                               DATA Types

Subscripting : Extracting particular character or multiple cgaracters from a string si called subscripting.
              Example : s = "hello"
                        print(s[0]) // output : h
                      or print("hello"[0])

1️⃣ Numeric Types (3)
int → Integer numbers (10, -5, 1000)

float → Decimal numbers (3.14, -0.5, 2.0)

complex → Complex numbers (2 + 3j, -1j)

2️⃣ Sequence Types (4)
str → Strings ("hello", 'Python')

list → Ordered, mutable collection ([1, 2, 3])

tuple → Ordered, immutable collection ((1, 2, 3))

range → Sequence of numbers (range(5) → 0,1,2,3,4)

3️⃣ Set Types (2)
set → Unordered, unique elements ({1, 2, 3})

frozenset → Immutable version of set

4️⃣ Mapping Type (1)
dict → Key-value pairs ({"name": "Akash", "age": 22})

5️⃣ Boolean Type (1)
bool → Boolean values (True, False)

6️⃣ Binary Types (3)
bytes → Immutable sequence of bytes

bytearray → Mutable sequence of bytes

memoryview → Memory view object of bytes

7️⃣ None Type (1)
NoneType → Represents absence of value (None)



📌 Summary
Category	Number of Data Types	Data Types
Numeric               	3      	int, float, complex
Sequence	       4	              str, list, tuple, range
Set	                2	          set, frozenset
Mapping	                1	      dict
Boolean	                1	      bool
Binary	                3	      bytes, bytearray, memoryview
None	                1	        NoneType
Total	                 14	

 Easy Trick to Remember
🔹 Numeric (Numbers) → int, float, complex
🔹 Sequence (Ordered) → str, list, tuple, range
🔹 Set (Unordered) → set, frozenset
🔹 Mapping (Key-Value) → dict
🔹 Boolean (True/False) → bool
🔹 Binary (Bytes) → bytes, bytearray, memoryview
🔹 None (No Value) → NoneType

 ## Examples of Data Types

1. Numeric Types
# Integer
x = 10  
print(type(x))  # <class 'int'>

# Float
y = 3.14  
print(type(y))  # <class 'float'>

# Complex
z = 2 + 3j  
print(type(z))  # <class 'complex'>


2. Sequence Types
# String
s = "Hello, Python!"  
print(type(s))  # <class 'str'>

# List (mutable)
lst = [1, 2, 3, "apple"]  
print(type(lst))  # <class 'list'>

# Tuple (immutable)
tup = (10, 20, 30, "banana")  
print(type(tup))  # <class 'tuple'>

# Range (generates sequence of numbers)
r = range(5)  # 0, 1, 2, 3, 4
print(type(r))  # <class 'range'>
print(list(r))  # Convert to list to see values

3. Set Types
# Set (unordered, unique values)
s = {1, 2, 3, 3, 4}  
print(type(s))  # <class 'set'>
print(s)  # {1, 2, 3, 4} (duplicates removed)

# Frozen set (immutable set)
fs = frozenset([5, 6, 7, 7])  
print(type(fs))  # <class 'frozenset'>

4. Mapping Type
# Dictionary (key-value pairs)
d = {"name": "Akash", "age": 22}  
print(type(d))  # <class 'dict'>
print(d["name"])  # Akash

5. Boolean Type
# Boolean
is_active = True  
is_done = False  
print(type(is_active))  # <class 'bool'>
print(is_active and is_done)  # False


6. Binary Types

# Bytes (immutable)
b = bytes([65, 66, 67])  
print(type(b))  # <class 'bytes'>
print(b)  # b'ABC'

# Bytearray (mutable)
ba = bytearray([68, 69, 70])  
print(type(ba))  # <class 'bytearray'>
ba[0] = 65  # Modifying the first byte
print(ba)  # b'AEF'

# Memoryview (view over bytes/bytearray)
mv = memoryview(bytes([72, 73, 74]))  
print(type(mv))  # <class 'memoryview'>
print(mv[0])  # 72 (ASCII for 'H')

7. None Type
# NoneType (absence of value)
x = None  
print(type(x))  # <class 'NoneType'> 
