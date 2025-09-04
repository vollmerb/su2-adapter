# SU2-preCICE adapter

This is a [preCICE](https://precice.org/) adapter for [SU2](https://su2code.github.io/) version 7.5.1 "Blackbird",
including examples for conjugate heat transfer and fluid-structure interation simulations.

Read more in the [documentation](https://precice.org/adapter-su2-overview.html).

**Note:** In its current state, the SU2 adapter is using the Python wrapper of SU2. The [previous implementation](https://github.com/precice/su2-adapter/tree/ab843878c1d43302a4f0c66e25dcb364b7787478) was directly editing the C++ source files of SU2. There is also a [version relying on the Python wrapper that however works with preCICE v2](https://github.com/precice/su2-adapter/commit/a87a1ed57e14dca97f1e47aab44632a254714004).

#Build instructions
Set the SU2_HOME variable
export SU2_HOME=/location/repo/SU2

Then run the adapter
./su2AdapterInstall

Then go to the SU2_HOME directory and run:
./meson.py build -Denable-pywrapper=true --prefix=/install_location/
./ninja -C build install

Then update the bashrc:
export SU2_RUN=...
export SU2_HOME=...
export PATH=$PATH:$SU2_RUN
export PYTHONPATH=$PYTHONPATH:$SU2_RUN
