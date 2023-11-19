# mini-snapshot
A small (<250 lines of code) snapshot testing library for python's unittest. This is a work in progress right now.

## Usage
```python
import unittest
from mini_snapshot import SnapshotTestCase

class MySnapshotTest(SnapshotTestCase):
    def test_something(self):
        value = ...  # code to test here
        # test that `value` matches the snapshot
        self.assertMatchesSnapshot(value)
```

## Features
- Working snapshot testing library
- Updating snapshots by setting environment variable `PY_SNAPSHOTTEST_UPDATE=1`
- It **shouldn't** cause any arbitrary code execution even if the snapshots aren't trusted
- Customizable snapshot formatting: define `_format_snapshot_` (single underscores, not double) on a class like you would do with `__repr__`
- Works on python 3.10+
## Future possible features
- Put it on pypi so that it can be installed easily with pip
- Cleaning unused snapshots in the `.snapshots` directory (how would that work with skipped tests)
- Perhaps a CLI so you don't have to fiddle with environment variables
- Interactive mode like jest
