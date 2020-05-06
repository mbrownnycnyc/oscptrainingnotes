# outline
* strings
* math
* variables & methods
* functions
* boolean expressions
* relational operators
* conditional statements
* lists
* tuple
* looping
* importing modules
* advanced strings
* dictionaries
* sockers
* tool building

# hash-bang
You should provide a `#!` at the beginning of your script in order to direct `bash` to call the proper script host.

* `#!/bin/python3`
* `#!/bin/bash`

# strings

## print string examples

````
print("Hello World!")
print('Hello World! string \n literal ')
print("""string is
multiline
""")
print ("con" + "cat like that")
````

# math

## arithmetic is supported
```
print(50+50)
print (50%6) #modulus (prints remainder)
print (50//6) #rounds to the whole decimal
print (50 ** 2) #exponents
```

# variables and methods

## variables
`something = "what"`

## calling a method
`print(something.upper())`

## call functions 
`print(len(something))`

## data types
```
name = "matt" #string
print(type(name)) #returns string
age = 36 #integer (does not round)
print(type(age)) #returns int
gpa = 1.3 #float
print(type(gpa)) #returns float
```

## casting data types (a cast is basically on-the-fly conversion of input... like a cast of a statue)
```
print(int(30))
print(int(age))
```

## concating different data types requires casting to proper data type
```
#succeeds
print("hello" + name)

#fails, because `age` is not an integer, and "I am " and " years old" are strings
print("I am " + age + " years old")

#succeeds because we cast age to string when concating
print("I am " + str(age) + " years old")`
```

### syntax tip: these two lines do the same exact thing:
```
age += 1
age = age + 1
```

# functions

## define the function 
```
# (remember coding is linear with time, top to bottom)
def who_am_i():
    name = "att"
    age = 36
    print("my name is " + name + ".  I am " + str(age) + " years old")`

```

## call the function you just defined
```
who_am_i()
```

# booleans

## equalities / comparison operators
```
= #sets something equal to something else
== #compares the left side to the right and returns a boolean (true, if they are the same, or false if they are not)
!= #compares the left side to the right and returns a boolean (true, if they are NOT the same, or false if they ARE the same... "!" means not)
```

# comparison and logical operators

```
and
or
not
```

# conditionals
```
# pass a parameter to the function `drink()`
def drink(money):
    if money >=2:
        return "got da drink"
    else:
        return "no drink"

print(drink(3)) #prints "got da drink"

# multiple parameters

def alcohol(age,money)
    if (age >= 21) and (money >= 5):
        return "got da drink"
    elif (age >= 21) and (money <= 5):
        return "not enough moolah"
    elif (age <>= 21) and (money >= 5):
        return "not old enough"
    else:
        return "wat."
```

# lists

items are stored in a list.
items are accessible by an index number (starting with 0).
items can be changed ('immutable").

```
movies = ["12 monkeys","fight club","enter the void"]
#print the full list out
print(movies)

#print a single item... remember we start count from 0 not 1
print(movies[0]) #prints "12 monkeys"

#print multiple items...
print(movies[2:4]) #prints items 2 through 4
print(movies[2:]) #prints items 2 through the end of the list
print(movies[:1]) #prints items from the beginning to item 1
print(movies[-1] #prints the single last item
print(len(movies)) #prints the total count of items in the list

#add an item
movies.append("the seventh seal")

#delete the last item
movies.pop()
#delete a specific item
movies.pop(0)
```

# tuples

tuples can't be changed ('immutable").

```
grades = ("a","b","c","d","f")
#there is no .apennd() method
print(grades[1])
```

# loops

## for..loops: iterates all list items
```
colors = ["red","blue","green"]
for item in vegatables:
    print(item)
```

## while..loops: executes while a condition is true
```
i = 1
while i < 10:
    print(i)
    i += 1
```

# modules

## defining a module
A module is a set of code that someone has written.  IT might be you, or someone else.

## importing a module
```
#sys is a module
import sys
print(sys.version)

from datetime import datetime as dt #specifies only a specific part of the namespace to import, assigning it hte alias "dt"
print( dt.now() )
```

# advanced strings
```
myname = "matt"
print(myname[0]) # a string is actually a list of characters

sentence = "what kind of hotel is this"
#split data
splitsentence = sentence.split()
print(splitsentence) #by default the string function `.split()` will take a string and create a list where each element is the element delimited by a space.

#join data
print(splitsentence.join(',')) #this will take the list `splitsentence` and create a string that is delimited by '," character.

#escape characters
quote = "my favorite line from Tommy Boy is \"what kind of hotel is this?\""
print(quote) #note that with double-quotes, some characters have specific meanings... an escape character tells the interpreter the character following that character should be treated as literal... meaning, `\"` is a "... and a `\\` is a \

#remove leading and trailing whitespace
unnecessarilyy_long_log_entry = "    log entry   "
print ( unnecessarilyy_long_log_entry.strip() ) # returns "log entry"

#conditional check
colors = ["red","blue","green"]
print ("red" in colors) #returns a boolean, if "red" is contained within the following list

#string interpolation
movie = ["fight club","12 monkeys"]
print ("a movie is {}, {}.".format(movie[0],movie[1])) #this will replace the `{}` with "fight club"

```


# dictionary

## define a dictionary
A dictionary is a key-value pair, as in, there is an item that is the key, and an item that is a value for that key.  You can't have two keys of the same value.

```
#consider a value can be of any data type
fruit = {"a":"apple","b":"banana"}

fruits = {"a": ["apple", "avocado", "apricot"], "b": ["banana", "blueberry"]}

#you can add key-value pairs to a dictionary:
fruits['c'] = ["cherry", "coconut"]

# you can change and append values:
fruits.update( {"a": ["apricot"] } )
fruits['c'] = "Cantaloupe"

#get the specific value of a key
fruits.get("c")
```

## sockets

```
#!/bin/python3

import socket

host = '127.0.0.1'
port = 7777

#this instatiates the socket: https://docs.python.org/3.8/library/socket.html#creating-sockets
target_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
target_socket.connect((host,port))
```

## creating a port scanner

```
#!/bin/python3

import sys, socket
import from datetime import datetime

#define our target
if ( len (sys.argv) == 2 ):
    target=socket.gethostbyname(sys.argv[1]) #translate hostname to ipv4
else:
    print("invalid arg count")
    print ("syntax: python3 scanner.py [ip]")

#add a header
print ( "-" * 50 )
print ( "Scanner target: " + targetip )
print ( "start time: " + str(datetime.now()) )
print ( "-" * 50 )

#try..catch
try:
    for port in range (50,85): #a range means a range between 50-85
        thesocket = socket.socket(socket.AF_INET, socker.SOCK_STREAM)
        socket.setdefaultimeout(1)
        result = thesocket.connect_ex((target,port))
        if result == 0:
            print("port {} is open.".format(port))
        thesocket.close()
except KeyboardInterrupt:
    print("\nexiting")
    sys.exit()

except socket.gaierror:
    print("hostname could not be resolved.")
    sys.exit()

except socket.error:
    print("couldn't connect to server.")
    sys.exit()
```