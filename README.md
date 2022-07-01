# Random Content Order Generator
This generates a 
- random order of items 
- to be occurring equal number of times
- that lasts the wished number of days
- based on date of the days
- starting from the given date in ISO format.

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