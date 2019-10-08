## DoltPy
This is DoltPy, the Python API for Dolt. Python is the language of choice for data science and data engineering, and thus we thought it would be wise to publish an API for building automated workflows on top of Dolt. 

### Installation
We are yet to publish this API to PyPi, but you can install from source using `pip` by cloning this repo into a directory, let's assume you used `doltpy`, then:
```bash
[doltpy] $ pip install .
```
Which will use `setup.py` to make the appropriate installation using a fresh build of the local copy of the source files.

### Usage
You will then have two commands at your disposal:
```bash
$ dolt-load --help
usage: dolt-load [-h] --dolt-dir DOLT_DIR [--commit] [--message MESSAGE]
                 [--branch BRANCH] [--dry-run]
                 dolt_load_module

positional arguments:
  dolt_load_module     Fully qualified path to a module providing a set of
                       loaders

optional arguments:
  -h, --help           show this help message and exit
  --dolt-dir DOLT_DIR  The directory of the Dolt repo being loaded to
  --commit
  --message MESSAGE    Commit message to assciate created commit (requires
                       --commit)
  --branch BRANCH      Branch to write to, default is master
  --dry-run            Print out parameters, but don't do anything
```
And then `dolthub-load` has an expanded set of tools for dealing with remotes:
```
$ dolthub-load --help
usage: dolthub-load [-h] [--dolt-dir DOLT_DIR] [--commit] [--message MESSAGE]
                    [--branch BRANCH] [--clone] --remote-url REMOTE_URL
                    [--remote-name REMOTE_NAME] [--push] [--dry-run]
                    dolt_load_module

positional arguments:
  dolt_load_module      Fully qualified path to a module providing a set of
                        loaders

optional arguments:
  -h, --help            show this help message and exit
  --dolt-dir DOLT_DIR   The directory of the Dolt repo being loaded to
  --commit
  --message MESSAGE     Commit message to assciate created commit (requires
                        --commit)
  --branch BRANCH       Branch to write to, default is master
  --clone               Clone the remote to the local machine
  --remote-url REMOTE_URL
                        DoltHub remote being used
  --remote-name REMOTE_NAME
                        Alias for remote, default is origin
  --push                Push changes to remote, must sepcify arg --remote
  --dry-run             Print out parameters, but don't do anything
```
Which will allow you to start using these scripts to load data into Dolt.

### Examples
See the [liquidata-etl-jobs](https://github.com/liquidata-inc/liquidata-etl-jobs) repo for examples.
