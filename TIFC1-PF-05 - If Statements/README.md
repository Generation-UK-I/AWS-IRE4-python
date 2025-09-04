# If Statements

## Learning Objectives: 
- What is an `if` statement and how are they used?
    - What is the correct syntax?
    - How do you structure if-elif-else to carry out multiple tests?
- What are Boolean Expressions?
- What are comparison operators?
- Using IF statements with Lists and Loops

---

## Back to Dinner… Weasley and Noche Problem
<img src="imgs/weasleyandnoche.jpg" width="300" />

## What Would Happen if I Ran This?

Think about what would happen if this piece of code ran. Walk through line by line and guess! The rest of this unit will break down the concepts seen in this piece of code and more. Let's dive in!

```py
foods = ['tuna', 'mackerel', 'salmon', 'sardines']

answer = input("What would you like to eat today boys?\n")

if answer.lower() == 'tuna':
    print(f"Okay, let's have {foods[0]} for dinner!" )
elif answer.lower() == 'mackerel':
    print(f"Okay, let's have {foods[1]} for dinner!")
elif answer.lower() == 'salmon':
    print(f"Okay, let's have {foods[2]} for dinner!")
elif answer == foods[3]:
    print(f"Okay, let's have {foods[3]} for dinner!")
else:
    print("Sorry boys! I only have chicken for dinner!")
```

---

## Boolean Expressions

This is a name for a conditional test - it is checking for whether or not something is TRUE or FALSE. 

You can imagine all of the use cases for this! 

## If Statements

If statements are conditional statements, they look at a true or false (*boolean*) test, then it runs some code based on the result.

The syntax for the if statement is as follows: 

```python
if [test]:
    code to run when test = true
else:
    code to run when test = false
```

An if statement can be used to represent various real-world scenarios, basically any time we make a decision. 

**If** traffic is light then I'll use the main road, otherwise (else) I'll take the back roads.

**If** it's going to rain I'll take an umbrella, else I won't. You might add a percentage to this, such as if there is greater than 30% chance of rain, then I'll take it.

When you're standing at the back of the queue in a coffee shop, you look at the counter and see there are only 2 croissants left. You might think, "**If** there are any croissants left then I'll have one. 

```py
if [croissant_available]:
    "I would like a croissant please"
```
Although the syntax is not technically correct, the concept of an if statement still applies. Python will look at that first line of code `if [croissant_available]:` and will evaluate whether this is true or false. This test could look at a simple integer variable which tracks the number of croissants, or something more advanced like checking a stock database. 

If your brain was running Python, when you reach the front of the queue you ask the cashier for a croissant, and if there is a `croissant_available` then you will respond by saying `I would like a croissant please`. If there are no croissants available, then the statement will be evaluated as false and that action will not run. 

In the previous example, if the test is false then nothing happens, and the application ends. Below we've added an `else` block, which runs when the test is false.

```py
if [croissant_available]:
    "I would like a croissant please"
else:
    "I would like a muffin please"
```
The last few examples have been written in `pseudo code`, which is a way of applying programming logic to a problem, but without worrying about syntax. This is very useful for brainstorming, and also useful to plan the logic of your code before you've actually decided what language to use - this is because most languages use the same structures i.e. `variables`, `loops`, `lists`, `if statements`, etc.

Now, let's take a look at an if statement with the correct Python syntax: 

```py
food = input("What would you like to order? \n")

if food.lower() == 'croissant':
    print("You have ordered a croissant!")
else:
    print("You have not ordered a croissant!")
```

Try running the above code; You're prompted to order something, currently our code only allows us to order a 'croissant' so type that in. Once you do do the test will evaluate to `TRUE` and you should see the response in the terminal `You have bought a croissant!`. 

If you order anything else, or make a typo,  then the value of `food` will not be equal to the string "croissant", so the `else` block of code will be executed.

Line 1: `food = input("What would you like to order? \n")` creates a variable called `food`, and it's value is a method called `input()` and a text string - *this string will usually explain the expected input*.

`input()` is used for capturing user input, so your app will print the provided string, pause, and wait for a response from the user. 

Once received the response will be stored in the variable `food`, and the value can be used elsewhere in your code. 

    We will review more uses of input() later on, however it is useful to add it now to make your code interactive.

Line 2: Begins the if statement, it's structure matches the pseudo-code, but we've got a real test in place. In this case `if food.lower() == 'croissant':`, which compares the value of the food variable, in lower case, against the word 'croissant'. This statement includes the comparison operator `==`. 

## Comparison Operators

A comparison operator in Python is used to compare two values and returns True or False based on the comparison. Below is a list of Python operators you can use with some example. Try running each of the examples to see the behavior of the code. You could also try changing the numbers to see how the code would react differently!

- Equal (==): Checks if two values are equal.
```py
x = 10
if x == 10:
    print("x is equal to 10")
```

- Not Equal (!=): Checks if two values are not equal.
```py
y = 5
if y != 10:
    print("y is not equal to 10")
```

- Greater Than (>): Checks if the value on the left is greater than the one on the right.
```py
a = 15
if a > 10:
    print("a is greater than 10")
```

- Less Than (<): Checks if the value on the left is less than the one on the right.
```py
b = 3
if b < 10:
    print("b is less than 10")
```

- Greater Than or Equal To (>=): Checks if the value on the left is greater than or equal to the one on the right.
```py
c = 7
if c >= 5:
    print("c is greater than or equal to 5")
```

- Less Than or Equal To (<=): Checks if the value on the left is less than or equal to the one on the right.
```py
d = 4
if d <= 4:
    print("d is less than or equal to 4")
```

Sometimes, you might also come across some word-based operators in Python. These each have differen use cases like the ones above. Take a look at some of them below and some examples:

- `and`: Combines two conditions and returns True only if both are true.
```py
number = 15

if number > 10 and number < 20:
    print("The number is between 10 and 20.")
```

- `or`: Combines two conditions and returns True if at least one of them is true.
```py
number = 3

if number < 5 or number > 100:
    print("The number is either less than 5 or greater than 100.")
```

- `not`: Negates a condition, returning True if the condition is false and False if it's true.
```py
number = 7

if number != 10:
    print("The number is not 10.")
```

The above three operators can be used with any data types in Python. They can also be combined with any of the other operators to add more conditions to your statement. Here is an example of using all three: 
```py
number = 120

if (number < 5 or number > 100) and number != 50:
    print("The number is either less than 5 or greater than 100, and it's not 50.")
```

- `is`: Checks if two variables point to the same object.
```py
number = 10

if number is 10:
    print("The number is exactly 10.")
```

- `is not`: Checks if two variables point to different objects.
```py
number = 20

if number is not 10:
    print("The number is not 10.")
```

- `in`: Checks if a value is present within an iterable (like a list, string, etc.). The following example will not be using a list, but usually this operator would be used to find a value within a list, tuple, etc... This example shows a value within a string.
```py
text = "hello world"

if "hello" in text:
    print("'hello' is found in the text.")
```

- `not in`: Checks if a value is not present within an iterable.
```py
text = "hello world"

if "goodbye" not in text:
    print("'goodbye' is not found in the text.")
```

There are any different operators Python uses to compare, the operators are very versatile and can be used in different use cases and wih different data types making Python a great general purpose language. 

## Elif and Else

Try running this piece of code and at the input prompt type anything other than 'croissant' and observe what happens.

```py
food = input("What would you like to order? \n")

if food.lower() == 'croissant':
    print("You have bought a croissant!")
else:
    print(f"We do not have any {food}")
```

In this example our `else` statement, which executes whenever the test is `FALSE`, shows how any value received from the `input()` method can be utilised within your code.

However, we do need to provide more options for our customers than just croissants. One way to do this is using `elif`.

```py
food = input("What would you like to order? \n")

if food.lower() == 'croissant':
    print("You have bought a croissant!")
elif food.lower() == 'cinnamon roll':
    print("You have ordered a cinnamon roll warmed up!")
else:
    print("This is not available... So I will go home!")
```

The `elif` statement stands for `else if`, which allows us to create a chain of additional conditions to test. 

1. If the opening test is `FALSE` the `elif` condition is evaluated.
1. If the `elif` condition is `TRUE` it's line of code is executed. 
1. If the `elif` is `FALSE` we again revert to the `else` block. 

The else block provides a fallback action if none of the preceding if or elif conditions are True.

We can use as many `elif` blocks as we like to expand our product selection: 

```py
food = input("What would you like to order? \n")

if food.lower() == 'croissant':
    print("You have bought a croissant!")
elif food.lower() == 'cinnamon roll':
    print("You have ordered a cinnamon roll warmed up!")
elif food.lower() == ' brownie':
    print("You have ordered a brownie, warmed up with a scoop of ice cream.")
elif food.lower() == 'cheese danish':
    print("You have ordered a cheese danish to go!")
else:
    print("This is not available... So I will go home!")
```

In this code we can start to see a problem emerging, which is our code becomes long and repetitive. A more efficient and cleaner approach would be to use our if statement to evaluate a list, which we can do with some of the comparison operators we looked at previously.

## Checking Whether an Item is not in a list

We can check if the value of a variable exists in a list of available items...

```py
foods = ['tuna', 'sardines', 'chicken', 'beef']
selection = 'avocado' # this line could also be 'selection = input("what would you like to order?")'

if selection not in foods:
    print(selection + " is not in stock, sorry!")
```

...complete it with an `else` block...

```py
foods = ['tuna', 'sardines', 'chicken', 'beef']
selection = 'avocado' # this line could also be 'selection = input("what would you like to order?")'

if selection not in foods:
    print(selection + " is not in stock, sorry!")
else:
    print(f"You have ordered {selection}")
```

## Using if statements with loops and lists

If statements are commonly paired with other Python features such **for loops**, allowing you to evaluate your `if` statements against every item in a list: 

```py
foods = ['tuna', 'sardines', 'chicken', 'beef', 'avocado']

for food in foods:
    if food == 'chicken':
        print(f"I know you don't like chicken, but this is good for you!")
    else:
        print(f"We have {food} in the pantry, let's eat!")
       
print("No more food! Goodbye!")
```

We could also use a `for loop` and an `if statement` to compare one entire list to another:

```py
lasagna_allergens = ['gluten', 'eggs', 'milk', 'soya', 'peanuts']
customer_allergies = ['eggs', 'milk']

for food in lasagna_allergens:
    if food in customer_allergies:
        print(f"Unfortunately this item has ingredients you're allergic to.")
    else:
        print(f"This item is suitable for your diet.")
       
print("No more food! Goodbye!")
```

If statements are very flexible, and allow us to plan and implement complex logic into our code, providing multiple pathways for processing, and multiple different outputs.

# Next Up: Complete the Exercises!!