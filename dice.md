We started by printing out a dice.

[ code on the way ]

Zane's crazy dice solution:
```python
import random
r = random.randint(1, 6)
C = 'o '
s = '-----\n|'+ C[r < 1] + ' ' + C[r < 3] + '|\n|'+ C[r < 5]
print s + C[r & 1] + s[:: -1]
```
