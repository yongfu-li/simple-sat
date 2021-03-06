simple-sat: Simple Python SAT Solver
====================================

This project is a simple recursive and iterative implementation of a
backtracking, watchlist-based, SAT solver. Code is based mostly on Knuth's
SAT0W program which can be found
`here <http://www-cs-faculty.stanford.edu/~uno/programs.html>`_. The iterative
code follows Knuth's version much closer, but is a bit more complicated. The
recursive version is rather straight-forward. Intended primarily to as a
learning tool.

Accompanying article can be found at
`http://sahandsaba.com/understanding-sat-by-implementing-a-simple-sat-solver-in-python.html
<http://sahandsaba.com/understanding-sat-by-implementing-a-simple-sat-solver-in-python.html>`_.


Usage
-----

.. code-block:: text

    usage: sat.py [-h] [-v] [-a] [-b] [--output_filter OUTPUT_FILTER] [-r]
                  [-i INPUT]

    Solve SAT instance by reading from stdin using an iterative or recursive
    watchlist-based backtracking algorithm. Iterative algorithm is used by
    default, unless the -r flag is given. Empty lines and lines starting with a #
    will be ignored.

    optional arguments:
      -h, --help            show this help message and exit
      -v, --verbose         verbose output.
      -a, --all             output all possible solutions.
      -b, --brief           brief output for assignemnts: outputs variables
                            assigned 1.
      --output_filter OUTPUT_FILTER
                            only output variables with namesstring with given
                            string.
      -r, --recursive       use the recursive backtracking algorithm.
      -i INPUT, --input INPUT
                            read from given file instead of stdin.

Example Usage
-------------

.. code-block:: text

    $ python sat.py -v --input test_input/simple/02.in
    Current watchlist:
    1: 1 2 3, 1 ~2
    ~1:
    2:
    ~2:
    3:
    ~3: ~1 ~3
    Current assignment: ~1 ~2 ~3
    Clause ~1 ~3 contradicted.
    Found satisfying assignment.
    ~1 ~2 3
