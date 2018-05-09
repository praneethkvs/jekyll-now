---
layout: post
title: If Else in List Comprehension, Python
---

In a python List Comprehension, the usual style of using an if statement is as below:

```python
["Even" for el in range(1,7) if el%2 == 0]
```
which goves you the output:
['Even', 'Even', 'Even']

But if we want to add an else clause to the above list the most intuitive way is to just add the else clause at the end as below:
```python
["Even" for el in range(1,7) if el%2 == 0 else "Odd"]
```
If you try to run the above code python throws an error, so we need to use a conditional expression which is not part of the list
comprehension syntax.

The correct way to do this is as follows:
```python
["Even" if el%2 == 0 else "Odd" for el in range(1,7)]
```
which gives the output:
['Odd', 'Even', 'Odd', 'Even', 'Odd', 'Even']

