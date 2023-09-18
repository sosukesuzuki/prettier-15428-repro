# [prettier/prettier#15428](https://github.com/prettier/prettier/issues/15428) minimal reproduction

## Overview

Prettier cannot ignore a directory includes file specified with `--ignore-path`.

```
$ cat ./dir1/.prettierignore
dir1/
dir2/
```

Both `dir1` and `dir2` should be ignored, but only `dir2` is ignored.

```
$ npm run format

> format
> prettier --write . --ignore-path ./dir1/.prettierignore

dir1/foo.js 23ms
package-lock.json 3ms
package.json 1ms
```
