General information about the CTL course available at https://ctl.polyphys.mat.ethz.ch/

# :wave: Solvent accessible surface area (SASA)

Consider a system composed of monodisperse spheres of identical radius *R* contained in a periodic cubic box of side length *L*. The spheres may partially overlap. Two out of the many interesting geometrical properties of such systems are the volume fraction of the spheres, and the part of the surface area of the spheres, so-called SASA(*r*) that is accessible by solvent spheres of radius *r*. For *r=0*, SASA is the total surface area of the spheres, and for *r*$\rightarrow\infty$, SASA approaches zero.  

## Task 1

Place *N* spheres of radius *R* randomly into a cubic box of side length *L*. Write the center coordinates of the *N* spheres to a file named coordinates.csv (*N* rows, 3 columns, blank-separated numbers). Estimate and return the volume fraction of the spheres of radius *R*. One Monte-Carlo-type approach consists of shooting randomly into the box volume and to then count the fraction *f* of shots that hit at least one of the spheres. The volume fraction is then estimated as &varphi; = *f*.

## Task 2

Read the coordinates of the spheres from a file named coordinates.csv, if it exists. Ask the user to enter a value for *R*. Return the estimated volume fraction &varphi;. 

## Task 3

Read the coordinates of the spheres from a file named coordinates.csv, if it exists. Otherwise ask the user to enter *N* and *R* and create a new system. Ask the user to enter a semipositive value for *r*. Estimate and return SASA(*r*), i.e., the surface area that can be reached by a sphere of radius *r*. 


