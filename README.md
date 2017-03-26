# bitterlich
Bitterlich angle count sampling simulation

The purpose of this is to simulate a forest, more specific a diameter distribution. 
With a monte-carlo approach, we want to verify if angle-count sampling yields correct results.

## purpose
To provide a repeatable, configurable simulation of angle count sampling to verify its correctness and determine its limits,
possibly even enabling the comparison of different inventory designs.

## parts
* Forest Simulation: can generate different diameter distributions
  * (maybe) Support for "patchwork" landscapes.
  * (maybe) simulation of irregular cross section shapes (ellipsoid or even more arbitrary)
   * See [On the Geometry of a Cross Section of a Stem](http://pub.epsilon.slu.se/10006/1/medd_statens_skogsforskningsinst_046_11.pdf)
       * how to generalize this? arbitrary convex polygons?
  * (maybe) height model, adding a 3rd dimension
  
* Sample Simulation (function of a point)
  * Simulate various sampling methods (Bitterlich, fixed radius, nested plot, etc).
  * (maybe) (temporal) movement and sampling simulation, to optimize for effort
  * (maybe) Simulated measurement errors (overestimating heights or diameters)

## tools
* Python based (v3 I guess?)
* (maybe) Matplotlib for vizualization
* NumPy for raster based data types and algorithms

## architecture
* Gui framework? Maybe Jupyter notebook for fast scaffolding
* Raster or vector? (vectors seem more sensible, but then are Matplotlib and Numpy still the right tools?)
  * Bitterlich's method is essentially geometric, vector seems the safer bet
  * A usable georeferenced geometry package is OGR
  * If we're going for vectors, we will be building a small GIS. Ideas for corresponding stacks [here](http://www.macwright.org/2012/10/31/gis-with-python-shapely-fiona.html).
  * Use mapnik for rendering instead of Matplotlib?
  * Or, considering complexity: Maybe we should avoid building a small GIS and script this inside QGIS instead? Rendenering, data structures and interfaces would be already there..
* Metric and USC units as a binary project-wide setting

## use cases
* forest simulation
    * generation (wizard)
    * saving and loading (forest file/data type)
    * rendering (trees on a 2d map)
* inventory design
    * definition of inventory (grid / density of plots, angle count factor, etc.)
    * saving and loading (inventory file/data type)
    * rendering (plots as overlay to the forest map)
* inventory execution
    * results output (textual summary and/or graphics)

## roadmap
### phase 1: setup
* 2d map
* tooling (tests, package manager, etc.)
* rough package structure
* first (non-parametrized) version of forest structure
    * rendered on the map
### phase 2: minimally viable product
* all use cases from above are covered (no special cases yet, just the __golden path__)
