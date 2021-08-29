# Indexing and Slicing

> *[`License`](https://github.com/bsoyka/python-guides/blob/main/LICENSE)*

Lists are easily one of the most powerful and versatile features of Python,
especially because of their slice notation. This applies to *all* sequential
data types in Python, including lists, tuples, and many more.

## Indexing

Before discussing slice notation in Python, we'll need to go over indexing. In
most programming languages, all sequential data types, such as lists, have
values that are assigned to indices.

In Python, indices always begin at `0`. This means the first item in a list is
at index `0`, the second at index `1`, and so on.

We'll start with a quick example:

```py
>>> students = ['Anne', 'Bob', 'Charlie']
>>> students[0]
'Anne'
>>> students[1]
'Bob'
>>> students[2]
'Charlie'
```

As you can see, you can access the items of a list (or other sequence) by an
index using square brackets.

### Negative indices

Python also has support for retrieving items by index starting at the end of a
sequence rather than the start. This is done by using negative indices, where
the last element is at index `-1`, the penultimate at index `-2`, and so on.

Going back to our previous example:

```py
>>> students[-1]
'Charlie'
>>> students[-2]
'Bob'
```

As shown, negative indices still use the same square bracket notation, just
with negative values.

### Assignment and deletion

Indexing can also be used to assign or delete specific list items (using
either positive or negative indices):

```py
>>> students[1] = 'Bill'  # Re-assign the second element
>>> students
['Anne', 'Bill', 'Charlie']

>>> students[-1] = "Chloe"  # Re-assign the last element
>>> students
['Anne', 'Bill', 'Chloe']
```

```py
>>> del students[1]  # Remove the second element
>>> students
['Anne', 'Charlie']
```

## Slicing

We can use slicing to access or update a sublist of a sequence rather than a
single element. Slice notation uses multiple indices to get a range of
elements from a list or other sequence.

### Syntax

The full syntax of slice notation is `start:stop:step`. Any of these three
parameters can be excluded to create incredibly powerful and custom slices.

`start` represents the index to start at when getting a sublist. This
parameter is inclusive, meaning the result will include the value.

`stop` tells at what index the sublist should end. Unlike `start`, this
parameter is exclusive, meaning the result will ***not*** include the element
at this index. Rather, it will include every value after/including the start
and before the stop.

`step` will allow you to take every nth element of a sequence. For example,
providing a `step` value of `2` would skip every other element in the list.

### Examples

Let's run through some examples now. We'll start off with a sample list:

```py
colors = ['Red', 'Orange', 'Yellow', 'Green', 'Blue', 'Purple']
```

The first example will retrieve everything in the list starting at (and
including) index `2` (Yellow) and ending at index `5` (Purple):

```py
>>> colors[2:5]
['Yellow', 'Green', 'Blue']
```

Notice specifically how `'Purple'` was not included in the result.

Next, we'll get every other element of the list. We'll leave out the `start`
and `stop` parameters so as to include the entire list:

```py
>>> colors[::2]
['Red', 'Yellow', 'Blue']
```

Take a look at how `'Orange'`, `'Green'`, and `'Purple'` were skipped. We can
also provide the `start` and `stop` to exclude some items, trying out negative
indices while we're at it:

```py
>>> colors[1:-2:2]
['Orange', 'Green']
```

The above example took everything in the list from (and including) `'Orange'`
to `'Green'` and skipped `'Yellow'` due to the value of the `skip` parameter.

### Reversing a sequence

We can also use a negative `step` value to reverse a list or other sequence,
as shown:

```py
>>> colors[::-1]
['Purple', 'Blue', 'Green', 'Yellow', 'Orange', 'Red']
```

### Substituting parts of lists

It's also possible to re-assign multiple list values at a time using slice
notation. For example:

```py
>>> colors[:3] = ['Crimson', 'Tangerine', 'Dandelion']
>>> colors
['Crimson', 'Tangerine', 'Dandelion', 'Green', 'Blue', 'Purple']
```

Note that the list of new values doesn't necessarily need to be the same
length as the original slice.
