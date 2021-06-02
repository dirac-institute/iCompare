# iCompare
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/maria8ch/iCompare/HEAD)
## Aims:
There are 4-5 integrators that everyone uses in Solar System dynamics that have never been fully compared and tested:
* OpenOrb
* FindOrb
* OrbFit
* JPL Horizons
* ADAM

We’d like to create an automated piece of code that propagates asteroids using all these integrators, compares their outputs, and presents it in some visually understandable way (e.g., a colourcoded matrix w. the asteroid on the Y axis and the integrator on the X axis).

More documentation will appear relative to completion rate.

## Currently available integrators
* OpenOrb using pyoorb (python bindings of OpenOrb)
* OrbFit via a Python wrapper that calls the OrbFit command-line code

## Currently available functionality
* receive ephemerides comparison via great circle distance in the form of a table 
* provide any asteroid or list of asteroids and receive visual comparison

## Future functionality
* parallelizing of code for asteroid lists
* addition of FindOrb to integrator suite
* please submit requests via pull request

## Requirements
* installation of OpenOrb and OrbFit, see here for OpenOrb: https://github.com/oorb/oorb, and here for OrbFit: http://adams.dm.unipi.it/orbfit/
