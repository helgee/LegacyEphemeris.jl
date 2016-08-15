# LegacyEphemeris

[![Build Status](https://travis-ci.org/helgee/LegacyEphemeris.jl.svg?branch=master)](https://travis-ci.org/helgee/LegacyEphemeris.jl)

[![Coverage Status](https://coveralls.io/repos/helgee/LegacyEphemeris.jl/badge.svg?branch=master&service=github)](https://coveralls.io/github/helgee/LegacyEphemeris.jl?branch=master)

[![codecov.io](http://codecov.io/github/helgee/LegacyEphemeris.jl/coverage.svg?branch=master)](http://codecov.io/github/helgee/LegacyEphemeris.jl?branch=master)

### Usage

```julia
using JPLEphemeris.ASCII

# Download and convert ephemeris DE421
getephem(421)

# Load ephemeris DE421
eph = Ephemeris(421)

# 2014-01-01T00:00 in Julian days
jd = 2456658.5

# Position of Mercury w.r.t. the Solar System's barycentre at 2014-01-01T00:00
# [km]
pos = position(eph, "mercury", jd)

# Velocity of Mercury w.r.t. the Solar System's barycentre at 2014-01-01T00:00
# [km/day]
vel = velocity(eph, "mercury", jd)

# Complete state vector (position and velocity) for a range of Julian days
st = state(eph, "mercury", jd:jd+100)

# The ephemeris also contains the set of constants with which it was calculated
# e.g. the Astronomical Unit (AU)
au = eph.constants["AU"]

# Close ephemeris file
close(eph)
```

### Available Celestial Bodies

* Mercury: `"mercury"`
* Venus: `"venus"`
* Earth-Moon system's barycenter: `"earthmoon"`
* Mars: `"mars"`
* Jupiter: `"jupiter"`
* Saturn: `"saturn"`
* Uranus: `"uranus"`
* Neptune: `"neptune"`
* Pluto: `"pluto"`
* Moon (geocentric): `"moon"`
* Sun: `"sun"`
* Librations: `"librations"`
* Nutations: `"nutations"`
