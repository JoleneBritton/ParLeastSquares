# Parallel Least Squares

Optimizes multiple inputs in parallel using the Levenberg-Marquadt algorithm.

# Requirements

- CMake >= 3.12
- Eigen3
- python3
- numpy

# Running Cell Wall Code
ssh into Marianas
```console
$ ssh -X {username}@constance.pnl.gov
$ ssh -X marianas.pnl.gov
```

Load in environment
```console
$ module load python/anaconda3.2019.3
$ module load cmake/3.15.3
$ source /qfs/projects/boltzmann/init_enviroment.sh
```

Navigate to correct directory

```console
$ cd ParLeastSquares
```

Rerun build file if made any changes (without --install if debugging or making modifications)

```console
./build.sh                 
./build.sh —install  
```

# Building

You may have to specify directories of dependencies, like so:

```console
$ mkdir build; cd build
$ cmake .. \
$   -DEigen3_DIR=/some/path
$ ctest
```

This will also output

# Testing

```console
$ mkdir build; cd build
$ cmake ..
$ make
$ ctest
```

Or you may optionally specify paths to folders with data for the tests:
```console
$ cmake .. -DDATA_PATH=/some/path
$ make
$ ctest
```

# Installation

You may install the python bindings like so (preferably using a virtual environment):
```console
$ python3 -m venv my_venv
$ source my_venv/bin/activate
$ python -m pip install --editable .
```
