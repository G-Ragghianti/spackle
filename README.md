# SpICL - System to manage spack installations

Developed for the Innovative Computing Laboratory at the University of Tennessee, Knoxville.

This system manages the update of a spack-based software installation to enable easy upgrade between spack verisons.  It accomplishes this by creating a new clone of the spack distribution and then reinstalling all software packages into the new spack installation.  It derives the spack software "specs" to install by searching an existing spack installation or by reading a simple list of specs from a file. This enable the software manager to ensure that all software is properly installed before switching users between the old and new spack-based software installations.

## Usage

The main utility is the bash script `install`.  The script takes two arguments:

`> ./install SOURCE_DIRECTORY DESTINATION_DIRECTORY`

The SOURCE_DIRECTORY is the pre-existing top-level spack directory from which you wish to build a list of software specs.

The DESTINATION_DIRECTORY is the desired location of the new spack installation.  If this directory does not exist, it will be created.  If no DESTINATION_DIRECTORY is provided, one will be created in the parent directory of the SOURCE_DIRECTORY with a name derived from the current date.

When the script is finished with all installations, it will print any failed specs to STDOUT and the file `failures.txt`.

## Installing upgraded packages

SpICL also includes a bash script `install_updates` which can be used to install newer versions of any currently installed packages.  It takes as its argument one path to a spack installation:

`./install_updates SPACK_INSTALLTION`

Similarlly, any failed specs are printed to STDOUT and the file `failures_updates.log`.

## Post-installation procedure

After the new spack installation is finished and packages are optionally upgraded, the system administrator can switch to the new spack-based software installations by pointing the /etc/profile.d/ scripts (or similar) to the modulefiles directories within the new spack installation.

