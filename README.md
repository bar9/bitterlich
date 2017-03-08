# bitterlich
Bitterlich angle count sampling simulation

The purpose of this is to simulate a forest, more specific a diameter distribution. 
With a monte-carlo approach, we want to verify if angle-count sampling yields correct results.

## purpose
To provide a repeatable, configurable simulation of angle count sampling to verify its correctness and determine its limits,
possibly even enabling the comparison of differen inventory designs

## parts
* Stand generation: can generate different diameter distributions
* bitterlich simulation (function of a point, yields basal area)
* (maybe) simulation of irregular cross section shapes (ellipsoid or even more arbitrary)
* (maybe) height model, adding a 3rd dimension
* (maybe) (temporal) movement and sampling simulation, to optimize for effort

## tools
* Python based (v3 I guess?)
* (maybe) Matplotlib for vizualization
* NumPy for raster based data types and algorithms

## architecture
* Gui framework? Maybe Jupyter notebook for fast scaffolding
* Raster or vector? (vectors seem more sensible, but then are Matplotlib and Numpy still the right tools?)
* Metric or USC units or both (Americans and Europeans collaborating...)
