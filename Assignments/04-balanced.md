# Assignment04 - Balanced Paraenthesis using Object oriented programming
### Due date: 05/16/2018 3:00pm

Solve Balanced Paraenthesis problem by creating a `Stack` datastructure
using `Python` classes.

1. Create a script `balacned.py` as follows:
    ```python
    import doctest


    class Stack(object):
        """
        Stack datastructure. To keep it simple, there is no
        upper bound for our stack. i.e you can put as many items
        as you can inside a stack and there will be no stack
        overflow.

        This is how stack should work:

        Create stack object to hold stack of items

        >>> stack = Stack()

        Initially stack will be empty.

        >>> stack.isEmpty()
        True

        Use .push() to push item in stack

        >>> stack.push("{")

        You can pop item from stack using .pop()

        >>> stack.pop()
        '{'

        Write a representation of your stack object.
        >>> stack.push("[")
        >>> stack.push("{")
        >>> stack.push("(")
        >>> stack
        <Stack with length: 3>

        >>> stack.pop()
        '('

        >>> repr(stack)
        '<Stack with length: 2>'

        Write a better string representation of stack
        >>> print stack
        Stack: [{
        >>> stack.push("(")
        >>> print stack
        Stack: [{(
        >>> str(stack)
        'Stack: [{('
        >>> "My stack is as follows: %s" % stack
        'My stack is as follows: Stack: [{('
        """

        def __init__(self):
            self.data = []

        # write remaining methods here


    MAPPING = {
        '}': '{',
        ']': '[',
        ')': '(',
    }


    def is_balanced(input_string):
        """
        Return True if all paraentheses are balanced, otherwise return False.

        >>> is_balanced("({})")
        True

        >>> is_balanced("({}[[]])")
        True

        >>> is_balanced("([]}")
        False

        >>> is_balanced("(((()")
        False

        >>> is_balanced("}")
        False

        >>> is_balanced("")
        True

        """
        stack = Stack()
        for item in input_string:
            if item in MAPPING.values():
                stack.push(item)
            else:
                if stack.isEmpty():
                    return False
                value = stack.pop()
                if value != MAPPING[item]:
                    return False

        if not stack.isEmpty():
            return False
        return True


    if __name__ == "__main__":
        doctest.testmod()
    ```

1. Complete `class Stack` so that all doctests will pass.

1. On completion you should see the output as follows:
    ```bash
    $ python2.7 balanced.py - v
    Trying:
        stack = Stack()
    Expecting nothing
    ok
    Trying:
        stack.isEmpty()
    Expecting:
        True
    ok
    Trying:
        stack.push("{")
    Expecting nothing
    ok
    Trying:
        stack.pop()
    Expecting:
        '{'
    ok
    Trying:
        stack.push("[")
    Expecting nothing
    ok
    Trying:
        stack.push("{")
    Expecting nothing
    ok
    Trying:
        stack.push("(")
    Expecting nothing
    ok
    Trying:
        stack
    Expecting:
        <Stack with length: 3 >
    ok
    Trying:
        stack.pop()
    Expecting:
        '('
    ok
    Trying:
        repr(stack)
    Expecting:
        '<Stack with length: 2>'
    ok
    Trying:
        print stack
    Expecting:
        Stack: [{
    ok
    Trying:
        stack.push("(")
    Expecting nothing
    ok
    Trying:
        print stack
    Expecting:
        Stack: [{(
    ok
    Trying:
        str(stack)
    Expecting:
        'Stack: [{('
    ok
    Trying:
        "My stack is as follows: %s" % stack
    Expecting:
        'My stack is as follows: Stack: [{('
    ok
    Trying:
        is_balanced("({})")
    Expecting:
        True
    ok
    Trying:
        is_balanced("({}[[]])")
    Expecting:
        True
    ok
    Trying:
        is_balanced("([]}")
    Expecting:
        False
    ok
    Trying:
        is_balanced("(((()")
    Expecting:
        False
    ok
    Trying:
        is_balanced("}")
    Expecting:
        False
    ok
    Trying:
        is_balanced("")
    Expecting:
        True
    ok
    7 items had no tests:
        __main__
        __main__.Stack.__init__
        __main__.Stack.__repr__
        __main__.Stack.__str__
        __main__.Stack.isEmpty
        __main__.Stack.pop
        __main__.Stack.push
    2 items passed all tests:
      15 tests in __main__.Stack
       6 tests in __main__.is_balanced
    21 tests in 9 items.
    21 passed and 0 failed.
    Test passed.
    ```
