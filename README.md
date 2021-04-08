# Documentation of QUIP+LAMMPS build on Wesleyan HPCC  

QUIP is built as a linkable library for LAMMPS following this [documentation](https://github.com/libAtoms/QUIP/blob/public/README.md).
So far the architectures linux_x86_64_ifort_gcc_openmp and linux_x86_64_ifort_icc_openmp have been built.
  
Starting with changing the architecture enviroment variable
```bash
export QUIP_ARCH=linux_x86_64_ifort_gcc_openmp
```

The make config file was then built inside the top level directory using
```bash
make config
```

All defaults were selected except for
```
Would you like to compile with GAP support?
```
which was selected as _y_,
```
Would you like to turn on QR decomposition for some GAP operations?
```
which was selected as _n_, and
```
Would you like to compile with preconditioned minimisation support?
```
which was selected as _n_ to prevent issues with the intel compiler (This could be tested, however given that ifort is Intel, I would suspect more issues to arrise).  

```bash
make libquip
```
_NOTE: This process takes some time (~20mins)_
