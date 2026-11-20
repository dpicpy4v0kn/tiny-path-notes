# Paths relative to a base directory

Use `relative_to` when the target is expected to be inside a known base.

```python
from pathlib import PurePosixPath

base = PurePosixPath("/project")
target = PurePosixPath("/project/data/items.csv")
assert target.relative_to(base) == PurePosixPath("data/items.csv")
```

A path outside the base raises `ValueError`. This is a lexical check and
does not inspect symbolic links or remove `..` components. For a check
against actual filesystem locations, resolve both paths first with
`Path.resolve()`.
