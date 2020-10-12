# SpICL - System to manage spack installations

Developed for the Innovative Computing Laboratory at the University of Tennessee, Knoxville.

This system manages the update of a spack-based software installation to enable easy upgrade between spack verisons.  It accomplishes this by creating a new clone of the spack distribution and then reinstalling all software packages into the new spack installation.  It derives the spack software "specs" to install by searching an existing spack installation or by reading a simple list of specs from a file. This enable the software manager to ensure that all software is properly installed before switching users between the old and new spack-base software installations.

## Usage

The main utility is the bash script "install".  The script takes two arguments:

`> ./install SOURCE_DIRECTORY DESTINATION_DIRECTORY`

The SOURCE_DIRECTORY is the pre-existing top-level spack directory from which you wish to build a list of software specs.

The DESTINATION_DIRECTORY is the desired location of the new spack installation.  If this directory does not exist, it will be created.  If no DESTINATION_DIRECTORY is provided, one will be created in the parent directory of the SOURCE_DIRECTORY with a name derived from the current date.

```
code
code
```
