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
...
T
* (aima-load 'all)
...
T
* (aima-compile)
...
T
* (test 'all)
...
 0 errors on system LANGUAGE
0
```


## Usage

At this point, you're ready to use the code that has been defined in the
various ``.lisp`` files. Looking at the tests may be helpful, for instance,
take a look at the test file ``agents/test-agents.lisp``.

In it, you will see an example for having an agent run in the "Wumpus world"
environment. You can call that directly:

```cl
* (run-environment (make-wumpus-world :max-steps 30))
```

For this exanple, you will see a series of Wumpus screens like so:

```
...
At Time step 6:
Agent [1 = -10006] perceives (NIL BREEZE NIL NIL NIL)
      and does (TURN LEFT)
    |----|----|----|----|----|----|
 5  | #  | #  | #  | #  | #  | #  |
    |----|----|----|----|----|----|
 4  | #  | O  | O  | W> | O  | #  |
    |----|----|----|----|----|----|
 3  | #  | O  |    |    |    | #  |
    |----|----|----|----|----|----|
 2  | #  | 1O | O  |    |    | #  |
    |----|----|----|----|----|----|
 1  | #  |    |    | O  | $  | #  |
    |----|----|----|----|----|----|
 0  | #  | #  | #  | #  | #  | #  |
    |----|----|----|----|----|----|
      0    1    2    3    4    5
#<WUMPUS-WORLD; Step: 6, Agents: [1 = -10006]>
...

```
