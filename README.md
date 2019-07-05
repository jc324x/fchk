# fchk # 

`fchk` is a small utility package, used in a few of my projects: 

- [git-in-sync](https://github.com/jychri/git-in-sync): Keep all of
  your git repos in sync across multiple computers
- [js2x](https://github.com/jychri/js2x): Convert Javascript to Markdown and beyond with js2x

Functions in package `fchk` return `bool` values, indicating the
status of files or folders.

The name is reduction of "file check".

### Example ###

``` go
// NotEmpty returns true if the target is an non-empty directory.
func NotEmpty(p string) bool {

	var f *os.File
	var err error

	if f, err = os.Open(p); err != nil {
		return false
	}

	if _, err = f.Readdir(1); err == io.EOF {
		return false
	}

	return true
}
```
