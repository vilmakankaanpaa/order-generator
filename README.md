# Random Content Order Generator
(Crossover study design)
This generates a dictionary with a date: item key-value pairs. The dictionary will have items in a random order suitable for a crossover study design.

Let's say we have 5 conditions A,B,C,D,E. We want to iterate this group several times, so that each condition occurs the same amount of time, but in a random order. For example, to repeat each condition three times, the generated order might be ABCDE, CDEAB, EABDC.

In addition, the generator takes an argument that describes for how many days each item should occurr, when it occurs. For example, we might want a condition A to occurr for 2 days instead of 1. Then the resulting dictionary will have conditions for each day in order like AABBCCDDEE, CCDDEEAABB, EEAABBDDCC.

In short:
- produces a dictionary with date-condition pairs
- each date is assigned a condition
- a given group of conditions will repeat, the conditions are in random order
- when a condition occurs, it will stay same for a wished number of days
- the dictionary starts from the given date in ISO format

## Testing the usage
On terminal, enter your Python3 IDE in the same directory as the python file:
```
$ python
```

in Python: 
```
import ordergenerator

items = ['lemur','dog','giraffe']
today = '2022-01-01'

ordergenerator.newOrder(content=items,startDate=today,occurrences=3,cycle=2)
```

There is now a new .txt file with the items occurring in random order but equal number of times. Each item "lasts" for the given number of days in the cycle.

To get the order in a dictionary (to use within other code):
(Enter the Python IDE to test on terminal)
```
import ordergenerator
dict = ordergenerator.getDictionary()
print(dict)
```

## Functions
### newOrder(content, startDate, occurrences, cycle)
Outputs a .txt file into the same directory with date and item pairs (e.g. '2022-01-01' 'lemur') in each line, created with the given parameters.

#### content (default: ['a','b','c'])
list of the items to be iterated
#### startDate (default: '2022-07-01')
the starting date of the study in ISO format ('YYYY-MM-DD')
#### occurrences (default: 7)
how many times an item should occur during the span of the study
#### cycle (default: 1)
how many days each item should be played in a row, when it occurs (i.e. cycle length in days)


### getDictionary()
Returns a dictionary with date as key and item as value. (e.g. { '2022.01-01' : 'lemur'})
