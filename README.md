# Emacs Lispeed

A set of programs and Emacs packages that share same goal - making Emacs Lisp more efficient.
```
Lispeed = Lisp + Speed
```

----

### Meta repository

This repository is not intended for active development.  
What you can find here:

* Project overview, as a whole.
* High-level documentation.
* Bundle of sources via submodules[1].
* Utility scripts and other niceties.

[1] You may want to clone all
included repositories by yourself, from their upstreams.

### Project

Emacs Lisp is slow.
Even with byte code compilation and all optimizations `byte-opt` provide,
it is slow.
When code that is executed goes beyond some threshold of
execution time, Emacs will **hang** for awhile due to it's
single-threaded nature.

Emacs users can benefit from better optimized Emacs Lisp.
It can reduce the amount and frequency of **annoying freezes**,
which in turn makes Emacs more responsive.

**Lispeed** is an attempt to improve builtin optimizer.  
[n2o.el](https://github.com/Quasilyte/n2o.el) implements additional
optimization levels after installed.

In order to do better optimizations some issues must be solved:

* **Dynamic typing**: [typ.el](https://github.com/Quasilyte/typ.el) library tries to infer arbitrary Emacs Lisp expression type.
* **Benchmark data analysis**: [benchstat.el](https://github.com/Quasilyte/benchstat.el) integrates [benchstat](https://godoc.org/golang.org/x/perf/cmd/benchstat), so that it can be used for Emacs Lisp.
* **Idioms identification**: [eldb](https://github.com/Quasilyte/eldb) is a big Emacs Lisp corpus that can be queried.

###  Getting the sources

This repository uses submodules. Use instructions below to fetch submodules.

```bash
# (1) With '--recursive' option:
git clone --recursive https://github.com/Quasilyte/emacs-lispeed/

# (2) Without '--recursive' option:
git clone https://github.com/Quasilyte/emacs-lispeed/
cd emacs-lispeed
git submodule update --init --recursive
``` 
