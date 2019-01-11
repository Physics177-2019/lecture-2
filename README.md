# Lecture 2: More Python, and numerical precision

As usual, material covered in class is in the [notebook](./lecture-2.ipynb). Some lecture notes on numerical precision are included below. These notes reference the official [Python documentation](https://docs.python.org/3/tutorial/floatingpoint.html) and some material from Chapter 4 of [Computational Physics](http://www-personal.umich.edu/~mejn/cp/chapters.html) by [Mark Newman](http://www-personal.umich.edu/~mejn/).

## Numerical precision

While integers in Python are represented with arbitrary precision, the precision of real or *floating point* numbers is limited. Typically, floating point numbers are represented by 64 bits of information: 1 bit for the sign, 11 bits for the exponent, and 52 for the significant digits.

Finite precision for real numbers has several consequences. First, it means that there is a limit to how large or how small of a number can be represented in Python. The largest number is around $10^308$, and the smallest around $10^{-308}$.

Second, not all decimals can be represented exactly in this binary form. For example, we know that it's impossible to write the fraction $1/3$ exactly as a decimal number in base 10. Similarly, the fraction $1/10 = 0.1$ is infinitely repeating in base 2. This can have strange consequences when we attempt to add such numbers together, if we expect infinitely precise results (see the [notebook](./lecture-2.ipynb) for more).

Third, precision will be lost when we try to compare numbers that differ dramatically in size, or numbers that almost perfectly cancel out. As a general rule we can assume that real numbers have about 16 significant figures -- anything beyond this is lost.
