---
aliases: /article/4448-nag-library
description: The Numerical Algorithm Group (NAG) Library
slug: nag-library
title: NAG Library
---

This article introduces the Fortran and C library of software under the
Numerical Algorithm Group (NAG) license. NAG Library is a collection of
robust, documented, tested and maintained numerical algorithms.

## Accessing the NAG Library

### Requesting access

If you wish to use the NAG Library on JASMIN you will need to request access
via the JASMIN Accounts Portal at:

<https://accounts.jasmin.ac.uk/services/additional_services/nerctools/>

This will give your JASMIN user account access to the "nerctools" Unix Group
that is used to limit access to NAG.

### Loading the NAG Library for use on JASMIN

The NAG library is made available via `module` command which is only available
once you are on the [scientific analysis servers]({{% ref "sci-servers" %}})
and [LOTUS cluster]({{% ref "lotus-overview" %}}) on JASMIN. In addition to
loading a module for the library, you will usually need to load a module for
the compiler you are using. For example:

{{<command user="user" host="sci1">}}
module load contrib/nag/25
module list
(out)Currently Loaded Modulefiles:
(out)    1) intel/fce/15.0.090   2) contrib/nag/25
{{</command>}}

The NAG library is loaded as well as the Intel Fortran compiler. Now you can
compile your code and link to the NAG library, for example:

{{<command user="user" host="sci1">}}
ifort your_code.f90 -lnag_nag -o your_code.exec
{{</command>}}

## How to find a NAG library routine

Please search the NAG documentation when looking for specific routines:

<https://www.nag.co.uk/numeric/fl/nagdoc_fl25/html/indexes/kwic.html>

## How to use the NAG library

The following shows the directory and file organisation of the materials.

```txt
/apps/contrib/nag/fll6i25dcl/

                    |- in.html  (Installer's Note - this document)
            |- doc -|- un.html  (Users' Note)
            |       |- lic_agr.txt  (license agreement)
            |
            |       |- libnag_nag.a      (static self-contained library
            |       |                     including NAG BLAS/LAPACK)
            |       |- libnag_nag.so.25  (shareable self-contained library
            |       |                     including NAG BLAS/LAPACK)
            |       |- libnag_nag.so     (symbolic link pointing at
            |- lib -|                     libnag_nag.so.26)
            |       |- libnag_mkl.a      (static library requiring
            |       |                     MKL BLAS/LAPACK)
            |       |- libnag_mkl.so.25  (shareable library requiring
            |       |                     MKL BLAS/LAPACK)
            |       |- libnag_mkl.so     (symbolic link pointing at
            |                             libnag_mkl.so.26)
fll6i25dcl -|
            |- nag_interface_blocks -|- *  (interface blocks for Intel compiler)
            |
            |            |- source --|- ??????e.f90
            |            |
            |- examples -|- data ----|- ??????e.d
            |            |           |- ??????e.opt
            |            |
            |            |- results -|- ??????e.r
            |
            |           |- nag_example*  (scripts to compile and run
            |- scripts -|                  NAG example programs)
            |           |
            |           |- nag_recompile_mods  (script to recompile
            |                                   interface blocks)
            |
            |- c_headers -|- * (C/C++ header file and information)
            |
            |- mkl_intel64_11.2.0 -|- *  (Intel Math Kernel Library)
            |
            |- rtl -|- *  (Intel compiler run-time libraries)
            |
            |           |- bin -|- *  (directories of license management
            |           |              binaries for supported platforms)
            |- license -|- README.txt
                        |
                        |- doc -|- *  (license management documentation)
```

## Further information

See the full NAG library manual at:

<https://www.nag.co.uk/numeric/fl/nagdoc_fl26/html/frontmatter/manconts.html>
