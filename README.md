# torch-modder-notes

Notes for torch maintainers/modders

# High-level concepts / tweaks / gotchas

## cutorch/cunn

* Be sure to `luarocks install FindCUDA` prior to doing any cutorch/cunn/cu-other-stuff development.  This will
mean that builds are incremental, rather than recompiling the entire project each time

## rpath

* For Mac OS X, Travis will happily run things just fine, even if you havent configured RPATH, by virtue
of the `LD_LIBRARY_PATH` and `DYLD_LIBRARY_PATH` settings in `torch-activate`.  If you want to replicate
behavior on a real Mac, which includes [System Integrity Protection](https://support.apple.com/en-us/HT204899)
activated by default, unset
`LD_LIBRARY_PATH` and `DYLD_LIBRARY_PATH` in travis build, and you can reproduce the weird bugs your 
users are probably having, and then fix them.

# Detailed code analysis

This is a "bit" out-of-date, but might provide some pointers.  Or you can update it, and submit a pull
request :-)
- [torch code analysis](torch-dev-notes.md)

