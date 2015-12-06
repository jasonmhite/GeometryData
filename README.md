I made an IPython notebook showing how I extracted this data from the problem object, which you can view
[here](data_extraction.ipynb).

## Source 

* location (meters): (158, 98)
* nominal intensity (counts per second): 3.2140e9

## Cross sections

Cross section data can be found in [`cross_sections.dat`](cross_sections.dat). These are **macroscopic** *total* cross sections,
so they effectively dictate the density as well. They are in units of `1 / meter`.

They are in the same order as the geometry dumped from the shapefiles! That is, the first value corresponds to the shapefile
that is first in `[problem object].domain.geometry` and so on.

## Detector locations

Locations for the detectors are in [`detector_locs.dat`](detector_locs.dat). Units are again in meters and the order
of that list is the ordering of the detectors (detector 1 is the first line, 2 is the second etc). There are 10
in total.

All of the detectors used the same values for dwell time, intrinsic efficiency and face area. These are:

* face area (m^2): .005806
* dwell time (seconds): 5
* efficiency (unitless): .62

## Observations

Observations are in [`observations.dat`](observations.dat). Each row is an experiment, while the column is the
detector number (corresponding to the ordering mentioned in the last section.)

Uncertainties are in [`uncertainties.dat`](uncertainties.dat). These are **standard deviations**, same format
as the observations.

There are 10 replicate sets of observations. You can generate more if you need to by simply calling the loaded
problem object without arguments (`P()`). The uncertainties are the square root of the value.

## Problem file

I have included the actual problem specification file I've been using, in [`spec.pkl`](spec.pkl). I can't 100%
guarantee that it will work and you might need to regenerate your own using the parameters I provided, but I think
it will so it's worth trying.
