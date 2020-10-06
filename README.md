# great-integrator-bake-off
## What a privilege and honour to be part of three months of research in a remote tent

### Aims:
There are 4-5 integrators that everyone uses in Solar System dynamics that have never been fully compared and tested:
* OpenOrb
* FindOrb
* OrbFit
* JPL Horizons
* ADAM

We’d like to create an automated piece of code that propagates asteroids using all these integrators, compares their outputs, and presents it in some visually understandable way (e.g., a red-yellow-green matrix w. the asteroid on the Y axis and the integrator on the X axis).

More documentation will appear relative to completion rate.
### Current progress and Milestones:

_Milestone 1_

Install OpenOrb. Using pyoorb (python bindings of OpenOrb), generate ephemerides as with JPL Horizons via Astropy.
Write a function which will take two series of ephemerides and compute the maximum difference metric. [DONE]

_Milestone 2_

Expand the work to OrbFit. Install OrbFit and learn how to run it on the command line. Write a Python wrapper that calls the OrbFit command-line code to integrate the same asteroid, as above. Compare it to JPL/Horizons output and see how well OrbFit is doing. [DONE]

_Milestone 3_

Extend the code so you can give it an arbitrary asteroid (not just 2019 OK). Run it for a few asteroids from each dynamical class (PHAs, NEOs, MBAs, Trojans, KBOs, etc..)

_Milestone 4_

Write code which makes these runs automatically, and computes the maximum difference metric.

_Milestone 5_

Write visualization code to generate a red/yellow/green table, given some thresholds of what is considered acceptable.

_Milestone 6_

Generalize to computing more metrics.

_Milestone 7_

Automate every stage of the code -- from installing to running -- so it’s easy to rerun for new versions of the code(s).

### Stretches
These are additional functionalities/ goals that may or may not be completed, depending on what time and resources allow.

_Stretch 1_

Enhance the generated reports based on how we like them. Expand the code to use ADAM and FindOrb, repeat the above. 

_Stretch 2_

Make the reports be a fancy web-accessible dashboard. 

_Stretch 3_

<<<<<<< HEAD
Finish DPS poster and/or complete a AAS research note.
=======
Finish DPS poster and/or complete a AAS research note.
>>>>>>> 8ae8fbb9cf6edc347729a4a05d8b94ede00e7112