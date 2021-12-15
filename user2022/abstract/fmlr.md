Introducing fmlr: A Novel High-Performance Matrix Framework for R
================
Drew Schmidt
12/15/2021

Out-of-the-box, R contains a wealth of matrix operations, mostly in
support of numerical computing on double precision data. There are also
numerous package extensions extending this core interface to additional
kinds of data, from the well-known Matrix package 1, to the gpuR
packages 2 for GPGPU, and of course far too many others to name here.
These extensions are generally focused on solving one particular
problem; for example, how do we do matrix computing from R on a GPU?

Although an abundance of narrowly-focused extensions is valuable for the
language, these come generally with one of two downsides. One is that do
not integrate well (or at all) with each other. Another is that these
extensions will almost always go out of their way to integrate with the
core R matrix framework. But that framework necessarily imposes some
performance penalties, such as modifying data in a copy, or having
extensions being wed to the slow S4.

To address these and other issues, we introduce the fmlr package 3. It
provides numerous matrix and statistics operations for both 32 and
64-bit floating point data, stored on CPU, GPU, or distributed across an
MPI cluster, all with a single, unified interface managed by R6 4.
Additionally, because our interface is entirely novel, we are able to
avoid some of the inherent performance penalties imposed by the R matrix
interface, including the two mentioned above. If accepted, we plan to
show the UseR attendee some of the capabilities of this new framework,
its syntax, and some example performance benchmarks.

<div id="refs">

<div id="ref-Matrix">

\[1\] D. Bates and M. Maechler, *Matrix: Sparse and dense matrix classes
and methods*. 2021.Available:
<https://CRAN.R-project.org/package=Matrix>

</div>

<div id="ref-gpur">

\[2\] C. Determan Jr, *GpuR: GPU functions for r objects*.
2019.Available: <https://github.com/cdeterman/gpuR>

</div>

<div id="ref-fmlr">

\[3\] D. Schmidt, *fmlr: Fused matrix library for r*. 2021.Available:
<https://hpcran.org/packages/fmlr/index.html>

</div>

<div id="ref-R6">

\[4\] W. Chang, *R6: Encapsulated classes with reference semantics*.
2021.Available: <https://CRAN.R-project.org/package=R6>

</div>

</div>
