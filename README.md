# cl-aima

*AIMA (AI: A Modern Approach) Code for Common Lisp*

The code here is the as that which appears in the following locations:
 * http://www.cs.berkeley.edu/~russell/code/code.tar.gz
 * http://aima.cs.berkeley.edu/lisp/code.tar.gz

More information about this code is available here:

 * http://aima.cs.berkeley.edu/lisp/doc/overview.html

The changes made are discussed in the file ``ChangeLog`` in this directory.


## Setup

Download the code and then start up SBCL:

```bash
$ git clone
$ cd cl-aima
$ sbcl
```

Load the code, compile it, and run the tests:

```cl
* (load "aima.lisp")
* (aima-load 'all)
* (aima-compile)
* (test 'all)
```


## Usage

TBD
