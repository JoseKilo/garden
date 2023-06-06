# How-to test an infinite loop

Let's say you have some code like this that you want to test:

```python
import time


def runner():
    while True:
        print("Iterating")
        time.sleep(0.1)
```

There are several approaches if you want to (and can) modify the loop itself.
For example, we can add a flag, so that the actual loop depends on it. And that
flag can be set using some `stop()` method or by patching it during tests.

But if you really can't modify the loop, there is an option using signals:

```python
import contextlib
import signal


class TimeoutException(Exception):
    pass


def timeout_handler(signum, frame):
    raise TimeoutException


@contextlib.contextmanager
def timeout(timeout):
    signal.signal(signal.SIGALRM, timeout_handler)
    signal.alarm(timeout)

    with contextlib.suppress(TimeoutException):
        yield

        # Cancel signal if not yet triggered
        signal.alarm(0)
```

You can use `timeout` in your tests like:

```python
def test_runner(capsys):
    with timeout(1):
        runner()

    captured = capsys.readouterr()
    assert captured.out.startswith("Iterating")
```

But keep in mind that `SIGALRM` is only available in Unix systems.
