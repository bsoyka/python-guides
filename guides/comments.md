# Comments

> *[`License`](https://github.com/bsoyka/python-guides/blob/main/LICENSE)*

Comments in any programming language are a great way to leave notes to
yourself and anyone else who might find your code in the future. You should
use comments to explain what your code does and why it's written the way it
is.

Comments are particularly easy to write in Python. There's only one way to do
it and it's pretty hard to mess up. Anything in your code followed by a `#` is
a comment.

It's recommended that you add a space after your `#` and before the text in
your comment to improve readability. If you add a comment after a line of
code, you should add two spaces before the `#` to make it easier to read.
Neither of these things is required, but they're encouraged and will make your
code and comments easier to read.

You can leave comments on the same lines as your code, in between lines, or
both!

These are all valid examples of comments:

```py
# This is a comment!
print(1 + 2)  # This is also a comment!

#This is a comment, too, but it should probably have a space after the #.
print(5)#There should be 2 spaces before the # and 1 after, but this is valid.

# This is a lot
# of comments in
# a row.
```

## Triple-quoted strings

Triple-quoted strings are often used to write multi-line comments. They are
interpreted as ordinary strings in Python, but they're typically used to write
documentation. Here's an example:

```py
"""
This is a triple-quoted string. We can put whatever we want in this string,
and it's usually used as a comment for documenting the code that follows.
"""
```

It's important to keep in mind that these strings aren't technically comments,
and they can be used as strings in your program too. For example:

```py
print("""Hello, world!""")
```
