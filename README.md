RandomIO
===============

`RandomIO` provides a readable interface for cryptographic quality random bytes.  It also allows generation of random files, dumping random bytes to files, and a `.read()` method for reading bytes.

### File generation

Generate a 100 byte file from a seed with one line:

```python
import RandomIO

path = RandomIO.RandomIO('seed string').genfile(100)
print(path)

# 'd719a1840dda1478e0518d67d7f0c0ec'
```

It is possible to specify the directory to generate the file in, or the file name

```python
# specify a directory:

path = RandomIO.RandomIO('seed string').genfile(100,'dir/')
print(path)

# 'dir/22aae6183b5202cd0c74381c673394d2'

# or file name:

path = RandomIO.RandomIO('seed string').genfile(100,'dir/file')
print(path)

# 'dir/file'
```

### Byte generation

Also allows reading random bytes and dumping those bytes to a file object.

```python
import RandomIO

s = RandomIO.RandomIO()
print(s.read(100))

# b'\x8bfT\x9c\x06_)\xa2,\xd0'

# or generate seeded random bytes
s = RandomIO.RandomIO('seed string')
print(s.read(100))

# b'\xc7\x15\xce7n\xaa\x8ca]u'

# dump the bytes into a file object
s = RandomIO.RandomIO('seed string')
with open('path/to/file','wb') as f:
	s.dump(10,f)

with open('path/to/file','rb') as f:
	print(f.read())
	
# b'\xc7\x15\xce7n\xaa\x8ca]u'
```


