# Modification to add in (defun) and (macro)

I implemented (macro ...) (begin ...) and (define ...) in the commented version of the 99 line Tiny Lisp. They are lightweight implementations in keeping with the spirit of Robert's work.

To build:

```shell
cc tinylisp-commented-defun.c -o tinylisp
chmod +x tinylisp
./tinylisp
```

I used the commented version, but feel free to port the changes into the minified version.

Here is an example run demonstrating some of the new capabilities:


```lisp
tinylisp
911>(defun square (x) (* x x))
square

885>(square 12)
144

885>(define list (lambda xs xs))
list

864>(macro (when c x)
       (list 'if c x ()))
when

828>(when #t 42)
42

828>(when #t (square 3))
9
```
