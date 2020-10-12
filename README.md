# SpICL - System to manage spack installations

Developed for the Innovative Computing Laboratory at the University of Tennessee, Knoxville.

This system manages the update of a spack-based software installation to enable easy upgrade between spack verisons.  It accomplishes this by creating a new clone of the spack distribution and then reinstalling all software packages into the new spack installation.  It derives the spack software "specs" to install by searching an existing spack installation or by reading a simple list of specs from a file.

`
code
code
`
