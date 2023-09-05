General information about the CTL course available at https://ctl.polyphys.mat.ethz.ch/

# :wave: Solvent accessible surface area (SASA)

Consider a system composed of filled monodisperse spheres of identical radius $R$ contained in a periodic cubic (3D) box, and surrounded by empty space or 'solvent'. The filled spheres may partially overlap. Two out of the many interesting geometrical properties of such systems are the volume fraction of the filled spheres, and the part of the surface area of the filled region, so-called SASA($r$) that is accessible by an additional 'solvent' sphere of radius $r$ that is fully located in the empty space but touches the surface of the filled region. For $r=0$, SASA is the total surface area of the filled region, and for $r\rightarrow\infty$, SASA approaches zero.  

## def generate_system($N$)

Place $N$ points (3D) randomly into a square (or cubic) box of unit side length $1$. Write the coordinates of the $N$ points to a file named coordinates.csv ($N$ rows, $3$ columns, blank-separated numbers). 

## def read_system

Read the coordinates of the spheres from a file named coordinates.csv. Determine $N$ and return $N$ and the coordinates. 

## def estimate_volume_fraction($N,\textrm{coordinates},R$)

Estimate and return the volume fraction of the $N$ spheres of radius $R$ inside the cubic box. One Monte-Carlo-type approach consists of shooting randomly into the unit box volume and to then count the fraction $f$ of shots that hit at least one of the filled spheres. The volume fraction $\phi$ is then estimated as $\phi=f$. Return the estimated volume fraction $\phi$. Note that periodic boundary conditions have to be taken into account properly. Some of the filled spheres may cross one or more boundaries of the periodic box. If this function is implemented using a number $S$ of random shots, you may add $S$ to the list of arguments of this function.

## def random_unit_vector

This function will be needed below. It creates a random 3D vector of unit length and returns this vector. To test if this function works, create $S$ random unit vectors ${\bf u}$, and calculate their mean squared $x$-component, i.e., $\langle u_x^2\rangle$. This should result in $1/3$. Also check if $\langle u_xu_y\rangle$ approaches zero if $S$ is increased to a large value like $S=10000$.

## def SASA($N,\textrm{coordinates},R,r$)

For the given system characterized by $R$, estimate and return SASA as function of $r$, i.e., the surface area that can be reached by a sphere of radius $r$. For the simplest case of $r=0$, one approach is again using a Monte-Carlo scheme. To this end, randomly shoot into the surface of a randomly selected filled sphere using the random_unit_vector function. Let us denote this point by $P$. Check, if this point $P$ is located inside any of the remaining filled spheres. If not, $P$ is said to be 'ok', located on the surface of the filled region, i.e., exposed to the solvent accessible space, and can be reached by a solvent particle of radius $r=0$. Repeat this procedure, create a large number $S$ of points $P$ and count the number of shots that are 'ok'. Denote ths number by $O$. The fraction of the total surface $A=N\times 4\pi R^2$ of the individual filled spheres that is accessible to solvent particles of radius $r=0$ is hence $O/S$. Accordingly, the estimated SASA($r=0$) value is SASA($r=0)=OA/S$.

Based on these considerations, develop a method to estimate SASA($r$) for $r>0$. Hint: A solvent particle of radius $r$ touching the surface at point $P$ can be inserted into the empty space only if the distance between the solvent particle's center and the centers of all the filled spheres is $r$ or larger.

## Application 1

Verify the applicability of the formula $\phi=1-\exp(-4\pi N R^3/3)$.

## Application 2

Use the above functions to create a system with $N=10$ spheres of radius $R=0.3$, estimate and print the volume fraction (with standard error), and plot SASA($r$) as function of $r$. 




