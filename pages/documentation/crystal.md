---
{title: Crystal structure, keywords: docs, sidebar: sw_sidebar, permalink: crystal,
  summary: Everything about defining crystal structure, folder: documentation, mathjax: 'true'}

---

 
This section introduces how to define a crystal structure.
 
## Definition of the lattice
 
For defining a spin Hamiltonian, first we need a magnetic lattice. SpinW builds magnetic lattices on top of crystal structures, so first we need to define a crystal structure. For simple magnetic lattices this seems to be an unnecessary extra step, however to model real systems with space group symmetry, defining a magnetic lattice on top of a crystal structure make things easier.
 
Before we define a new crystal structure, we initialize an empty SpinW object:
```matlab
model = spinw
model.lattice
```
*Output*
```
  struct with fields:
        angle: [1.5708 1.5708 1.5708]
    lat_const: [3 3 3]
          sym: [3×4×0 double]
       origin: [0 0 0]
        label: 'P 0'
```
 
The [spinw.lattice](spinw_lattice) property will store all the information that defines the lattice (without the atoms). The default values give a cubic lattice (angles are stored in radian) with a lattice parameter of 3 Å and no symmetry (`spinw.lattice.sym` field is empty).
 
The [spinw.genlattice](spinw_genlattice) function can be used to modify the lattice:
```matlab
model.genlattice('lat_const',[2.71 2.71 13],'angled',[90 90 120],'spgr','R -3 m')
model.lattice
```
*Output*
```
  struct with fields:
        angle: [1.5708 1.5708 2.0944]
    lat_const: [2.7100 2.7100 13]
          sym: [3×4×36 double]
       origin: [0 0 0]
        label: 'R -3 m'
```
 
Here we modified the lattice parameters and angles (the `angled` parameter takes angles in units of degree) and defined a space group. Space groups with standard settings can be added simply by using its name, e.g. `'R -3 m'` which corresponds to the labels stored in the `symmetry.dat` file (to see the content of this file type `edit symmetry.dat` into the Matlab Command Window). The `spgr` option also accepts directly space group operators, see section [symmetry](symmetry).
 
## Generation of crytal structure
## Coordinate systems
## Lattice transformations
## Atomic properties


{% include links.html %}
