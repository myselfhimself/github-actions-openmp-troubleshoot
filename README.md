# Github Actions OpenMP troubleshooting
Ensures that OpenMP runs properly on Github Actions Ubuntu images/kernel online.
In C but intended for a Python/C++ project troubleshooting. See [this upstream issue](https://github.com/actions/virtual-environments/issues/1465).

OpenMP C code comes from [this tutorial](https://computing.llnl.gov/tutorials/openMP/exercise.html) by the Lawrence Livermore National Laboratory.

Thanks to this project, a fix was found, [this G'MIC Python binding issue is now solved](https://github.com/myselfhimself/gmic-py/issues/47).

The fix was to set `OMP_NUM_THREADS` to a value `>= 1` on environments where the number of threads is low or 0 (including the Github Actions online build bots).

The `.actrc` file is for providing the proper Docker image to the [nektos/act](https://github.com/nektos/act) local Github Actions Worfklow testing tool.
