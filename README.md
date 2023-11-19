# mini-snapshot
A small (<250 lines of code) snapshot testing library for python's unittest. This is a work in progress right now.

## Usage
```python
import unittest
import mini_snapshot

class MySnapshotTest(SnapshotTestCase):
    def test_something(self):
        value = ...  # code to test here
        # test that `value` matches the snapshot
        self.assertMatchesSnapshot(value)
```
