#Attitude Estimator#
**Author:** Philipp Allgeuer

**Version:** 1.0.1

**Date:** 16/05/14

##General Overview##
Attitude Estimator is a generic platform-independent C++ library that implements an IMU sensor fusion algorithm. Up to 3-axis gyroscope, accelerometer and magnetometer data can be processed into a full 3D quaternion orientation estimate, with the use of a nonlinear Passive Complementary Filter. The library is targeted at robotic applications, but is by no means limited to this. Features of the estimator include gyro bias estimation, transient quick learning phases, tuneable estimator parameters, and near-global stability backed by theoretical analysis.

Great emphasis has been placed on having a very efficient, yet totally numerically and algorithmically robust implementation of the filter. The code size has also been kept to a minimum, and has been extremely well-commented. The programmatic interface has also been made as easy to use as possible. Please refer to the extensive documentation of the library for more information on its capabilities and usage caveats.

Attitude Estimator was developed as part of the [NimbRo-OP](http://www.nimbro.net/OP/) project at the University of Bonn.

##Feature List##
- Small and highly efficient performance-oriented cross-platform C++ library
- Implements fusion of IMU sensor data (3-axis gyroscope, 3-axis accelerometer, 3-axis magnetometer), forming a reliable 3D attitude (orientation) estimate in the form of a quaternion
- Able to dynamically deal with missing or non-present sensor data, even if there is theoretically no longer enough information to reconstruct a full 3D attitude
- Gyro bias estimation, tuneable algorithm parameters, interface to provide state/system priors if desired
- Transient quick learning phase for fast initial settling of the attitude estimate
- Guaranteed numerical and algorithmic stability, with much effort having gone into ensuring the complete robustness of the implementation
- Independent code with no external dependencies other than certain maths functions of the C++ Standard Library
- Documented using the Doxygen documentation generation tool, including a code sample and a discussion of all usage caveats
- Extremely well-commented library source code detailing and discussing the implementation details
- Tried and tested by the author in simulation and on various robotic platforms

##Installation##
This library is implemented as a collection of platform-independent C++ source files. To get started just clone the `attitude_estimator` repository.

There are three ways of using the library:
1. Directly include the source files in your project, and build them with the rest of your project.
2. Build a static library (e.g. `*.a` or `*.lib`) of the source code and link your project to it.
3. Build a dynamic library (e.g. `*.so` or `*.dll`) of the source code and link your project to it.

Due to the small and efficient nature of the library, one of the first two options is recommended. Very minimal benefit is expected from building a dynamic library.

Note that as at release `v1.0.1`, the required source files are simply `attitude_estimator.h` and `attitude_estimator.cpp`.

A sample makefile for building the static and dynamic libraries using `gcc` is included in the release. As mentioned in the makefile however, the Attitude Estimator could equivalently be built using any other compiler, such as for example MSVC.

##Dependencies##
The library does not require C++11, and has no external dependencies other than the C++ Standard Library, of which only `cmath` is required. More precisely, the only standard library functions that are required are `abs`, `sqrt`, `asin` and `atan2`.

##Documentation##
###Doxygen Documentation###
The first place to look for help and guidance when trying to use the Attitude Estimator is the Doxygen documentation. This can be generated by running `Attitude Estimator vX.X.X/doc/generate_doc.sh`, and is then located at:

`Attitude Estimator vX.X.X/doc/Attitude Estimator.html`

Or equivalently:

`Attitude Estimator vX.X.X/doc/out/html/index.html`

The Doxygen documentation provides a complete explanation of the entire library, including all caveats and details, and includes a code sample to make the task of integrating the library into user code as simple as possible. Complete documentation of all functions, classes and namespaces of the library is also included. As such, the Doxygen documentation is intended to be the primary help resource when working with the library.

###Source Code###
If anything is not adequately explained in the Doxygen documentation, or more details as to the inner workings of the library are required, the next place to look would be in the library source code. The code is extremely well-commented and should thus be fairly self-explanatory. A good starting point is `attitude_estimator.h`.

###Where To Get More Help?###
If neither the Doxygen documentation nor a look into the source code can resolve your issues for whatever reason, you can contact the author at the email address given in the *Bugs and Improvements* section.

##Bugs and Improvements##
I welcome all feedback, suggestions and bug reports. If you improve or fix anything about the library then I encourage you to let me know so that the library can be improved for everyone!

**Email:** `pallgeuer[at]ais.uni-bonn.de`
