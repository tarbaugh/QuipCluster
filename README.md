# Documentation of QUIP+LAMMPS on Wesleyan HPCC  


QUIP Build:
QUIP is built as a linkable library for LAMMPS following this [documentation](https://github.com/libAtoms/QUIP/blob/public/README.md).
Architecture was selected as linux_x86_64_ifort_gcc_openmp using,
```bash
export QUIP_ARCH=linux_x86_64_ifort_gcc_openmp
```
this was done in attempt to match the LAMMPS build with KOKKOS for GPU support as detailed in _/share/apps/CENTOS7/lammps/3Mar2020.install_

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
