# mynewt_hc-sr04

A simple test library to connect a HC-sr04 ultrasonic distance sensor the mynewt core platform.

# Including in your mynewt project.

Add the following repository descriptor to your `project.yml` file

```
repository.mynewt_hc-sr04:
    type: github
    vers: 0-latest
    user: paulfdietrich
    repo: mynewt_hc-sr04
```

and include the following in your `project.repositories` variable

```
project.repositories:
    - apache-mynewt-core
    - mynewt_hc-sr04
```

Add the following dependency to your application's (or whatever uses this library) `pkg.yml` file.

```
pkg.deps:
    ...
    - "@mynewt_hc-sr04/libs/hc-sr04"
```
    
# Limitations

This was mostly just a test library so I could test creating packages,
projects, and repositories.  It has some severe limitations

* It can only control one device per build
* It relies on polling GPI and GPO for timing

# Usage

## Include files

Add the include path `#include <hcsr04/hcsr04.h>` to files that are using
the library.

## hcsr04_init


```
void hcsr04_init(void);
```
Initializes the library to talk to the sensor.  The sensor is expected
to be attached to two port pins, which you must define in your BSP.
This must be called once.  A good place is 

## hcsr04_measure_distance

Return the distance in centimeters of the object near your HC-SR04.  If
a reading is not possible or the object is too far away, `-1` is returned.

```
int hcsr04_measure_distance(void);
```


## Unresolved Externals

You will get several unresolved externals 
