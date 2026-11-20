# Inspecting path components

Use Python's `pathlib` to inspect a path without touching the filesystem.

```python
from pathlib import PurePosixPath

path = PurePosixPath("reports/weekly/summary.csv")
assert path.parts == ("reports", "weekly", "summary.csv")
assert path.parent == PurePosixPath("reports/weekly")
assert path.stem == "summary"
assert path.suffix == ".csv"
```

Use `PureWindowsPath` to inspect Windows paths on any operating system.
A filename such as `archive.tar.gz` has a final suffix of `.gz`. Use
`suffixes` to get both extensions.
