# Read/Write file
```Python
f = open("demofile.txt", "r")
```

* `'r'` - Read
* `'w'` - Write - will create a file if the specified file does not exist
* `'a'` - Append
* `'x'` - Create - will create a file, returns an error if the file exist

## After open
* `f.read()` - read the whole file. `Param:` number of characters
* `f.readline()`
* `f.write("what to write")`
* `f.close()`
