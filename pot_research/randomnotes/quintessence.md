
```python
from timeit import repeat

times = repeat(
    lambda: sum(range(1000)),
    repeat=5,
    number=10000,
)

print(times)


from timeit import timeit

elapsed = timeit(
    lambda: sum(range(1000)),
    number=10000,
)

print(elapsed)
```