TIL 2020-10-27

I typically use `zip` to interleave two lists of equal length:

```
In [1]: chars = ['a', 'b', 'c']
In [2]: counts = [1, 2, 3]
In [3]: interleaved = list(zip(chars, counts))
In [4]: interleaved
Out[4]: [('a', 1), ('b', 2), ('c', 3)]
```

There's a handy trick for going in the other direction:

```
In [5]: separated = list(zip(*interleaved))
In [6]: separated
Out[6]: [('a', 'b', 'c'), (1, 2, 3)]
```

The asterisk unpacks the argument `interleaved`, so `zip` receives three tuples as arguments. From the `zip` docs:
```
Returns an iterator of tuples, where the i-th tuple contains the i-th element from each of the argument sequences or iterables.
```

Since each argument has two elements, we should expect zip to return two tuples -- the first containing all the elements at index 0 (chars) and the second containing all the elements at index 1 (counts).

Neat-o!
