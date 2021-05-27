---
layout: post
title: "From Molecular Model to Sturctural Factor"
date: 2021-05-21
progress: 10%
permalink: /xtal/fcalc/
---

{% epigraph 'Go back to definition!' 'George Polya' 'How to solve it' %}

In general, the following equation calculate the complex x-ray scattering factors from molecular models{% sidenote '1' 'Usually a PDB file, with infos of space group, atom type, atom position, iso/aniso B-factor, and occupancy in an asymmetric unit.' %}{% sidenote "2" "Rupp's textbook, P279" %}:

$$
F_{p} (\vec{h}) = \sum_G \sum_j O_j \cdot f_{\vec{h},j}\cdot\text{DWF}\cdot\exp{[2\pi i \vec{h}\cdot(\mathbf{R}_G\vec{x}_j+\vec{T}_G)]} \tag{1}
$$

where: 

1. subscript $$p$$ of $$F_p$$ stands for "protein", as there is extra correction from solvent; 

2. $$\vec{h}$$ is the reciprocal index $$[h,k,l]$$; 

3. $$G$$ is the index of symmetry operations (appears as rotation matrix $$\mathbf{R}_G$$ and translation vector $$\vec{T}_G$$) belonging to the space group; 

4. $$j$$ is the index of atom; $$O_j$$ is the occupancy value the atom $$j$$; 

5. $$f_{\vec{h},j}$$ is the atomic scattering factor of atom $$j$$ at reciprocal space site $$[h,k,l]$$;

6. DWF is the debye-waller factor or B-factor, either isotropic or anisotropic

7. $$\vec{x}_j$$ is the <i class='contrast'>fractional</i> coordinates{% sidenote '3' 'In contrast to cartesian coordinates.' %} of atom $$j$$ in the unit cell.

I will cover discussions on practical calculation of some nontrivial terms mentioned above, a full `python` version codes can be find [here](https://github.com/Hekstra-Lab/vae-refinement/blob/main/src/Fmodel.py).

* listnotshown
{: toc}

### <i class='contrast'>Space group and symmetry operations</i>

As the atoms contained in the PDB file is an asymmetry unit, we have to apply all necessary symmetry operations on the asyymetry unit to complete the unit cell. The symmetry operations list is fully determined by the space group info, which is usually recorded as `CRYST1` entry in PDB file. For example in [`6QJI`](https://www.rcsb.org/structure/6QJI):

```
CRYST1   61.970   61.970  228.365  90.00  90.00 120.00 P 31 1 2
```
where the space group is $$P3_112$$, with operations{% sidenote '4' 'See Rupp Textbook P226 about how to translate Hermann-Mauguin symbol into list of operations.' %}: 
1. x, y, z

2. -y, x-y, z+1/3

3. -x+y, -x, z+2/3

4. -y, -x, -z+2/3

5. -x+y, y, -z+1/3

6. x, x-y, -z

Each operation can be represented as a rotation matrix $$\mathbf{R}_G$$ and a transliation vector $$\vec{T}_G$$, like for the opearation 2, (-y, x-y, z+1/3): 

$$
\mathbf{R}_G=\left[\begin{array}{rrr}
0 & -1 & 0\\
1 & -1 & 0 \\
0 & 0 & 1
\end{array}\right] \quad \vec{T}_G = [0,0,1/3]
$$

`gemmi` provides a good API to generate a complete list of operations based on the space group symbol:

```python
>>> symmetry = gemmi.SpaceGroup("P 31 1 2")
>>> operations = list[symmetry.operations()]
>>> print(operations[1], operations[1].rot, operations[1].tran)
<gemmi.Op("-y,x-y,z+1/3")> [[0, -24, 0], [24, -24, 0], [0, 0, 24]] [0, 0, 8]
```

### <i class='contrast'>Space group and symmetry operations</i>
