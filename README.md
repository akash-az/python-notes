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

# type() : returns the type of data
         Example :name = "akash"
                 type(name) // <class, 'str'> 


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



### TYPE CASTING

Scenario: Taking User Input (String to Integer/Float)
Problem:
User input is always a string. We need to convert it into a number for calculations.

price = input("Enter product price: ")  # User enters "500"
tax = input("Enter tax percentage: ")   # User enters "10"

# Convert input from string to float for calculation
price = float(price)
tax = float(tax)

total_price = price + (price * tax / 100)
print(f"Total price after tax: {total_price}")
🔹 Explanation:
✅ input() returns a string → Convert it to float for calculation.
✅ Without conversion, Python would raise an error when trying to perform arithmetic.

2️⃣ Scenario: Rounding Off a Decimal Value (Float to Integer)
Problem:
We get float values from calculations, but we need a rounded whole number.

total_marks = 485.75
rounded_marks = int(total_marks)  # Truncate decimal part

print(f"Final Marks (Rounded): {rounded_marks}")
🔹 Explanation:
✅ int() removes the decimal part (not rounding, just truncation).
✅ If rounding is needed, use round() instead:

print(round(485.75))  # Output: 486
3️⃣ Scenario: Combining Strings and Numbers (Number to String)
Problem:
Python does not allow direct string + number concatenation.

age = 25
message = "I am " + str(age) + " years old."  # Convert int to str

print(message)  
🔹 Explanation:
✅ str(age) converts 25 to "25", allowing string concatenation.
✅ Without conversion, Python throws an error.

4️⃣ Scenario: Removing Duplicates from a List (List to Set)
Problem:
A list may have duplicate items. We need a unique collection.

students = ["Akash", "Rohan", "Akash", "Neha", "Rohan"]
unique_students = list(set(students))  # Convert list → set (removes duplicates) → list

print(unique_students)  
🔹 Explanation:
✅ set() removes duplicates.
✅ list(set()) converts it back to a list.

5️⃣ Scenario: Using dict() for Key-Value Pair Conversion
Problem:
Data from an API or file may come in list of tuples, which we need as a dictionary.

student_data = [("name", "Akash"), ("age", 22), ("course", "MCA")]
student_dict = dict(student_data)

print(student_dict)  # {'name': 'Akash', 'age': 22, 'course': 'MCA'}
🔹 Explanation:
✅ dict() converts [(key, value)] pairs into a dictionary.

6️⃣ Scenario: Iterating Over a Range (String to Integer)
Problem:
A program takes input for the number of iterations but input() returns a string.

num = input("Enter how many times to print: ")  # "3"
num = int(num)  # Convert to int

for i in range(num):
    print("Hello, Python!")
🔹 Explanation:
✅ int(num) allows range(num) to work.
✅ Without conversion, Python throws an error.

7️⃣ Scenario: Extracting Numeric Data from Strings (String to Float)
Problem:
We get numeric values as part of strings, but we need them as numbers.

text = "The price is 299.99 dollars"
price = float(text.split()[3])  # Extract "299.99" and convert to float

print(f"Extracted Price: {price}")  
🔹 Explanation:
✅ text.split()[3] → Extracts "299.99" as a string.
✅ float() converts it to a number.

8️⃣ Scenario: Saving Memory Using tuple() (List to Tuple)
Problem:
Lists use more memory than tuples. If data is fixed, use tuples.

months_list = ["Jan", "Feb", "Mar", "Apr"]
months_tuple = tuple(months_list)

print(months_tuple)  # ('Jan', 'Feb', 'Mar', 'Apr')
🔹 Explanation:
✅ Tuples are faster and memory-efficient compared to lists.
✅ Use tuple() when data won’t change.

🚀 Summary of Practical Use Cases
Scenario	From → To	Why?
User Input Conversion	str → int/float	For mathematical operations
Rounding Off	float → int	To remove decimals
String Concatenation	int → str	To combine numbers with strings
Removing Duplicates	list → set → list	To get unique elements
Creating a Dictionary	list of tuples → dict	To structure data
Looping with Input	str → int	range() needs integers
Extracting Numbers from Text	str → float	To perform calculations
Optimizing Memory	list → tuple	Tuples are faster


## Coding Exercise :

1- Input two digit number and print the sum of these two digits.

# solution : s1 = input("Enter 2 digit number\n");
num1 = int(s1[0])
num2 = int(s1[1])

print(f"sum of 2 digits is : {num1+num2}")

2- BMI Calculator
Solution :
 s1 = float(input("Enter your height in m\n"))
weight = float(input("Enter your weight in kg\n"))

print("BMI is : ",round(weight/(s1*s1)) )

** floor division value : print(8 // 3) returns 2.
** print(round(8/3)) : prints 3.(rounds of 2.66)
** print(round(2.666666,3))

3- Print the age entered in days,months,weeks

Solution :
Age = input("Enter your age\n")
age_left = 90 - int(Age)
months_left = age_left*12
days_left = age_left*365
weeks_left = age_left*51
print(f"you have {days_left} Days,{months_left} Months,{weeks_left} Weeks")

4- Tip Calculator :

print("Welcome to the tip calculator")
bill = float(input("please enter the bill amount $\n"))
tip = int(input("please enter the tip percentage 5,10,12,15 \n "))
people = int(input("no of people the bill will split in \n"))

tip_percent = round((bill * (tip/100)),2)
print(tip_percent)
total_amount = float(bill + tip_percent)
print(total_amount)

individual_amount = round((total_amount/people),2) # round does not always displays result in 2 precision. Also round only affects the display but internally float still stores the original value.

print(f"amount for each : ${individual_amount:.2f}") #formatfunction ":.2f" makes surethe precision.


