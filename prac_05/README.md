# Practical 05 - Dictionaries

**Did you finish last week's work? Including the practice section?**  
If not, make sure to complete it during the week. The more you practise, the better you'll learn.   
If you have any questions, ask your peers or tutor the following week.


# Walkthrough Example

Copy the code from: [state_names.py](state_names.py)

This is a program that uses a 'constant' (name is ALL_CAPS) dictionary to store the Australian state abbreviations and
names - e.g., QLD is Queensland. It asks the user for their 'short' state and prints the full state name by looking it up
in the dictionary.  
**Note:** not all dictionaries will be constants! This one makes sense, since we won't be changing the states anytime
soon.

## Modifications

1. Run the program to see how it works.

2. Currently, the code formatting is incorrect. Note: Sometimes when you copy code into PyCharm it already fixes the formatting for you!   
   Dictionary literals should be formatted with no space before, and one space after, the colon,
   like `{"A": 1, "B": 2}`  
   Thankfully, PyCharm knows this and can fix all of your formatting problems for you!
   If you move your mouse over the grey line near the first colon, PyCharm pops up the problem... Click on it to see the
   action icon (light bulb) to the left... Click on that to see the options... Choose reformat file... Problem solved.  
   You can also choose **Code > Reformat Code** or use the keyboard shortcut any time. It does the whole file or
   whatever is selected. No more excuses for bad formatting! Seriously, always fix your formatting :)   
   This is also a great way to learn what the "PEP 8" standards are for Python code formatting style.  
   ![PyCharm PEP 8 warning](../images/05image4.png)

3. Currently, the program requires you to enter the states in capitals. Change the program so lowercase inputs also work
   to show the state names. (There are two places to add a string method.)

   ![Pencil icon](../images/03image1.png)
4. Do this next part on paper first (then in PyCharm):  
   Write a loop that prints all the states and names **neatly lined up**
   with string formatting, like:

       NSW is New South Wales
       QLD is Queensland
       NT  is Northern Territory

# Intermediate Exercises

File: `hex_colours.py`

Based on the state name example program above, create a program that allows you to look up hexadecimal colour codes like
those at
[http://www.color-hex.com/color-names.html](http://www.color-hex.com/color-names.html)

Use a constant dictionary of about 10 colour names and write a program that allows a user to enter a name and get the
code, e.g., entering
**AliceBlue** should show **#f0f8ff**.

Entering an invalid colour name should not crash the program.  
Allow the user to enter names until they enter a blank one to stop the loop.

**Note:** We have just done two exercises that use dictionaries that are constants and named in ALL_CAPS. Please do not
think this is any kind of rule or pattern. Dictionaries that change would not be constants.

# Do-from-scratch Exercises

## Word Counts

File: `word_occurrences.py`

Write a program to count how many times words exist in a string.  
The program should ask the user for a string, then print
the counts of how many of each word are in the string.  
Example output:

    Text: this is a collection of words of nice words this is a fun thing it is
    a : 2
    collection : 1
    fun : 1
    is : 3
    it : 1
    nice : 1
    of : 2
    thing : 1
    this : 2
    words : 2

**Hints:** use a dictionary where the keys are the words and the values are the counts; when you find a word, check if
it's in the dictionary...

- Notice that the sample output is sorted.  
  *Only after* you have the program working, **make your program do this sorting**.

- As a further refinement, **align the outputs so the numbers are in one nice column**. You will need to find the
  longest word in the list first.  
  Then you can use the string `format` method to take a variable
  width. This can be done with another `{}` placeholder, like:

  ```python
  print("{:{}} = {}".format(x, y, z))
  ```

  This formats the first placeholder value, x, with a width of y then prints a literal = then the value of z.  
  (Note that x, y and z are not intended to be meaningful names.)
  Your output should then look something like:

      a :          2
      collection : 1
      fun :        1

## Emails

File: `emails.py`

Write a program that stores users' emails (unique keys) and names (values) in a dictionary.  
Ask the user for their email until they enter a blank one.  
Use a separate function to get the name from the email as in the example below.  
You should find the following methods useful: `split`, `join`, `title`.  
Notice the prompt to check if the name is correct: `Y/n`  
This is used in console programs (like in Linux etc.) so you can just press Enter to accept the default, which is Yes.
If it's not correct, ask the user for their name.  
Once you have stored all the emails and names, just loop through the dictionary (use the `items()` method) and print
them out.

    Email: lindsay.ward@jcu.edu.au
    Is your name Lindsay Ward? (Y/n)
    Email: abe@gmail.com
    Is your name Abe? (Y/n) y
    Email: jimbo546@hotmail.com
    Is your name Jimbo546? (Y/n) no
    Name: Jim Boh
    Email: 
    
    Lindsay Ward (lindsay.ward@jcu.edu.au)
    Abe (Abe@gmail.com)
    Jim Boh (jimbo546@hotmail.com)

## Tariffs

File: `tariffs.py`

In practical 1, you should have created an electricity bill estimator using constant values for the tariff amounts like:

```python
TARIFF_11 = 0.244618
TARIFF_31 = 0.136928
```
 
   Electricity bill estimator 2.0   
   Which tariff? 11 or 31: 11       
   Enter daily use in kWh: 13.4     
   Enter number of billing days: 90 
   Estimated bill: $295.01         

Now create a version of the above electricity program that uses a
**dictionary** to store the tariffs and the corresponding cost.  
In the prompt, list all the tariffs (all the dictionary keys)
and make sure a valid one is selected.  
Use the appropriate cost from the dictionary to calculate the bill total.

You will need to change how you present the "Which tariff" prompt, since these values come from the dictionary.

To show the benefit of this, **add three more tariffs** (just make them up).  
You should find that this is a very simple step for you, and your program can handle it without any extra coding.

# Practice & Extension Work

## Practice

1. Write a program that uses a dictionary to store and look up your friends' names and addresses. Assume you don't have
   many friends :) and none of them share the same name
   (this means the name can be the unique key for the dictionary). Create a simple menu for your program, which should
   allow you to do the following
   (remember to implement this incrementally, one bit at a time):

    - Enter a new name & address
    - Change an address for an existing entry
    - Print the address for a name you choose

## Extension

1. Convert parallel lists into a dictionary...

   Recall that it's possible to represent information in the form of parallel lists where the indices determine how the
   information is related across lists. For example:

   ```python
   names = ["Jack", "Jill", "Harry"]
   dates_of_birth = [(12, 4, 1999), (1, 1, 2000), (27, 3, 1982)]  
   ```

   This means Jack was born on 12/4/1999, Jill was born on 1/1/2000, and Harry was born on 27/3/1982.  
   Write a program using a dictionary instead of the above parallel lists that allows the user to enter the
   date-of-birth details for 5 people, and have it display their individual ages.  
   **Hint:** you can **split()** a string like "12/4/1999", as we did in the lecture last week.

2. Write a function that takes two parallel lists as input parameters and returns a dictionary where keys are from the
   first list and the values are from the second. Use the above example as a test case.

3. Extend your name & address program with file loading and saving
   (and any other fun things you'd like to add).

# Deliverables

This section summarises the expectations for marking in this practical.

- `state_names.py`
- `hex_colours.py`
- `word_occurrences.py`
- `emails.py`
- `tariffs.py`
