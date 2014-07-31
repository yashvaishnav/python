We started by printing out a dice.

[ code on the way ]

Our solution using a list of indexes:
```python
import random
def printSequence(sequence):
	printable = [" _____ ", "|     |", "| o   |", "|  o  |", "|   o |", "| o o |", "|_____|"]
	for index in sequence:
		print printable[index]
rolled = random.randint(1, 6)
if rolled is 1:
	printSequence([0, 1, 3, 1, 6])
if rolled is 2:
	printSequence([0, 2, 1, 4, 6])
if rolled is 3:
	printSequence([0, 2, 3, 4, 6])
if rolled is 4:
	printSequence([0, 5, 1, 5, 6])
if rolled is 5:
	printSequence([0, 5, 3, 5, 6])
if rolled is 6:
	printSequence([0, 5, 5, 5, 6])
```

Zane's crazy dice solution:
```python
import random
r = random.randint(1, 6)
C = 'o '
s = '-----\n|'+ C[r < 1] + ' ' + C[r < 3] + '|\n|'+ C[r < 5]
print s + C[r & 1] + s[:: -1]
```
