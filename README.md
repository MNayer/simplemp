# SimpleMP
Simple multiprocessing and logging (SimpleMP) provides a solution to the two problems:
1. Logging while using python multiprocessing.
2. Stopping spawned processes using CTRL+C.

## Install
```bash
pip install simplemp
```

## Example
```python
from simplemp import parallel, addlogging, execute


@addlogging
def square(x):
    logger.info("Square: %d" % x)
    return x * x


@addlogging
@parallel
def process(x):
    y = square(x)
    logger.info("Input %d, output %d." (x, y))
    return True


if __name__ == "__main__":
    execute(process, it=range(20), nprocs=3)
```
