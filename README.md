# mpfr_f
another Fortran module for MPFR

(... work in progress ...)

This module has been inspired by [FMPFR](https://github.com/tkoenig1/FMPFR), with the following differences:
* [MPFR](https://mpfr.org) variables can be created on the stack, thus avoiding allocations where possible,
* all variables must be explicitly cleared after the last use (call `MPI_CLEAR_F`),
* arithmetic is done by calling the wrapper functions, instead of having overloaded arithmetic operators (except for assignments and comparisons),
* many operations have yet to be implemented.

The operations for which the API has remained unchanged here can be called using their original MPFR function names.
Otherwise, the functions have mostly been wrapped into subroutines with their names having '_F' appended.
Many routines have somewhat misleadingly been declared `PURE` to assist in calling them from other pure code.
Please check the source code for more information.
