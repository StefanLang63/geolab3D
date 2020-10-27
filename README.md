# geolab3D
Toolbox for algorithms around 2D and 3D geometric objects.

In the broadest sense, every function in this toolbox takes geometric objects as input, and produces geometric objects as result. Dependend on the function, additional input parameters may be necessary, such as tolerance values.

Geometric objects in the context of this project are parametric one- or two-dimensional manifolds embedded in 2-Space or
3-Space, i. e. 2D and 3D parametric curves and surfaces.

All functions produce (a) parametric geometric object(s) as output which represent(s) all points that are part of the solution.
If such (a) geometric object(s) cannot be computed directly, the result may instead provide a functor that allows the evaluation
of any point within the valid parameter range of the result set (and if the parametric range cannot be computed exactly, a functor
is provided for that as well). Such functors may be approximated with splines on demand, using machine precision as tolerance value.

The calculations should stay absolutely precise (within machine limits) up to the point where we need an actual result, at which
point all functors (if any) are evaluated. Postponing this evaluation should help to improve optimization and parallelization efforts.

Use of implicit objects: An alternative to representing a geometric option are implicit representations, i. e. a set of points that
is characterized by fulfilling a specific equation. E. g. distance(X,M)==r specifies all points X on a spherical surface with a
radius of r around the point M. It's unclear whether or under which circumstances such representations might be used or even be
superior to using an equivalent parametric representation.


## Examples of functions

  * construction of basic 2D and 3D geometric objects
  * definition of Bezier and NURBS spline curves and surfaces
  * trimming and untrimming of curves and surfaces
  * merging of joined curves and surfaces
  * analysis of object properties such as continuity, curvature, or being of a specific geometric type
  * distance, nearest points, and intersections of two geometric objects.


## Advanced topics

### Healing functions
a toolbox of algorithms to analyze a set of geometric objects for assumed properties, and fix those geometries
as needed.

### Geometric solver
a toolbox of algorithms stored in a an expert system together with processing statistics such as time complexity.
The purpose of this solver is to find suitable combinations of stored algorithms to find the result set for a specific operation,
and select the best candidate regarding complexity and other processing statistics automatically.

### Processing factory
a process that analyses a given set of processing orders for their potential to be processed in parallel on the
CPU or GPU. Also responsible for providing visual feedback on the current state of processing and pointing out bottlenecks.

