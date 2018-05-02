# Assignment03 - Balanced Paraenthesis
### Due date: 05/09/2018 9:00pm

1. Create a script `balanced_paraentheses.py` as follows:

```python


def is_balanced(input_string):
    """
    Function to detect that paraenthesis specified in `input_string`
    are balacned.

    Returns True if balanced else return False
    """
    print "Given input: %s" % input_string
    
    # complete this function


if __name__ == "__main__":
    print is_balanced("({[]})")
    print is_balanced("(){}[]([])")
    print is_balanced("[]{]")
    print is_balanced("([]}")
```

2. Complete `pattern` function so that it will print a pattern when you run the script.

3. Run script on Terminal(or command prompt) as follows

```bash
$ python2.7 balanced_parentheses.py
Given input: ({[]})
True
Given input: (){}[]([])
True
Given input: []{]
False
Given input: ([]}
False
```
