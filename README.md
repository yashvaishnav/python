Python Day 1
======

Welcome to Python! In order to ease the load on the instructor in the classroom, we are going to start using this GitHub repository to share problems and keep everyone working at their own pace. There will be an instructor to guide the learning, but we expect that you make a commitment to attempting to solve your problems indepedently, rather than becoming dependent on the instructor for help.

**The only way you'll learn coding is if you struggle through the errors.**

Today, we're going to use Python to answer the question *How many Friday the 13ths have passed since January 1st, 1900?*? We'll get started by using loops to answer this question.

### The `range` function
Recall how to use `range`. The `range` function produces a list with a specified number of elements. Below, we made a list containing every year from 1900 to 2014.
```python
years = range(1900, 2015)
```
*Notice how the range goes from `1900` to `2015`, not to `2014`*. This is because the range function takes in a number to start counting from and the number to end at, and doesn't include the ending number.

Try printing out every year in the list.
```python
years = range(1900, 2015)
for y in years:
	print y
```

### Counting with a variable
Recall how to make variables and increment them. To create a variable, just think of a name that has no spaces or punctuation that you've not used yet, and give it a starting value.
```python
thisIsAVariable = 5
```

Let's make a variable to count how many years have passed since 1900.
```python
count = 0
```

For every year in my list, I want to make count increase by `1`. Do you remember the syntax for doing this?
```python
count = count + 1
```

When we put this all together, it will look something like this.
```python
count = 0
years = range(1900, 2015)
for y in years:
	count = count + 1

print count
```

At the end, what's printed out is the count for the number of years. 

### Counting months

Let's say that we now want to count the number of months. The trivial way to do this would be to change the amount that `count` increases by, to `12`.
```python
count = count + 12
```

Alternatively, we could make a list for the months and loop through it, adding `1` to `count` each time.
```python
months = range(1, 13)
years = range(1900, 2015)
count = 0

for y in years:
	for m in months:
		count = count + 1

print count
```

Notice the indentation. The indentation is indicating that *for every year in my list of years, go to every month in my list of months, and add 1 to count for each month.* The indentation is very important.

### Counting days

Can you extend this to counting the number of days? That is, *how many days are there between January 1st, 1900 and December 31st, 2014?*

Some pointers for this part of the problem:
 - You'll have to make another list.
 - You'll have to add another loop and indent it appropriately.
 - Assume every month has 30 days.

### Accounting for different month lengths

As you may know, different months have different numbers of days. In the `for` loop for months, you will have to check the month and do the corresponding loop.

Here's an example where we loop through the months of the year and print something different out for each month.
```python
months = range(1, 13)
for m in months:
	if m is 1:
		print "I was born in January!"
	if m is 2:
		print "I never got Valentine's day cards when I was a kid."
	
	# check the other months
	
	if m is 11:
		print "Thanksgiving!"
	if m is 12:
		print "Christmas is the best time of the year."
```

You can apply the same idea to loop through a different list of days based on which month it is. Some guidelines for completing this part of the problem:
 - use Google to find out the number of days in each month
 - use a loop to count the number of days (it will be useful later when we count Friday the 13ths)
 - try to find a more efficient way to check months using `or` in the `if` condition.

### Account for leap years

If you were able to count days as expected (without accounting for leap years), you should have gotten a count of `41975`. If you got a number close to this but not exactly this, check your `range` functions to ensure that you are creating a list with an accurate number of elements.

Now try accounting for leap years. This will involve refining the `if` conditions you wrote for the code above to take the `y` variable (the one looping through `years`) into account.

Some guidelines for this part of the problem:
 - Every 4 years, there is a leap year.
 - Every 100 years, there is no leap year (ignoring the every 4 years rule).
 - Every 400 years, there is a leap year (ignoring the every 100 years rule).

### Print out every day

At this point, it's a good idea to print out every year - month - day combination to make sure your loops are set up correctly. 

Let's do a quick recap on how to print out things that combine `int`s (numbers) and `str`s (text). For example, if I had a variable `x` set to `4`, I could print out its value as so:
```python
x = 4
print "x = " + str(x)
```

The `str` function converts the input `x` into text, that it can then add to the `"x = "` to produce `"x = 4"`. You can use the same idea to print out the current calendar day.
```python
print str(m) + " / " + str(d) + " / " + str(y)
```

### Print out the weekday as well

We're going to give a little less guidance with this one. The basic idea is that you print out which day of the week it is along with every date that you print out. That is, instead of
```
...
7 / 7 / 2014
```

your program prints out
```
...
Monday, 7 / 7 / 2014
```

Think about how to represent each day of the week, and how to have that representation change as days of the week do.

### Count Friday the 13ths

If you're at this point, you are close to counting the number of Friday the 13ths. All you need now is an `if` condition that checks if the weekday is Friday, and the day of the week is `13`. You should get `198`.


