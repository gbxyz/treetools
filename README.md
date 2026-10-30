# treetools - simple scripts for managing directory trees.

## 1. dedupe

`dedupe` finds and removes duplicate files within a directory tree.

### Usage

```
dedupe OPTIONS
```

#### Options

* `--report` -- report rather than backup/delete (default behaviour)
* `--backup=DST` - location where backups should be put
* `--delete` - whether to delete duplicates
* `--symlink` - whether to symlink duplicates
* `--exclude=PATTERN` - exclude files matching this regexp
* `--match=PATTERN` - include files matching this regexp
* `--keep=(oldest|newest|highest)` - keep the oldest, newest or highest (in the tree) file.

Only one of `--backup`, `--delete`, `--symlink` or `--report` can be used.

## 2. treemerge

`treemerge` losslessly merges two directory trees. If a file exists in the same (relative) location in both trees, the
file in the "from" tree will not be removed unless the "to" file is identical. The "from" tree will only contain files that could not be safely moved to the "to" tree.

### Usage

```
treemerge FROM TO
````
