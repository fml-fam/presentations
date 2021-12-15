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

Most of these kinds of matrix extensions operate at the R level. As
such, they will almost always go out of their way to integrate with the
core R matrix framework. But that necessarily imposes some performance
penalties, such as modifying data in a copy, or having extensions being
wed to S4, which can make iterated methods very slow. Other approaches
to tackle this problem include the well-known RcppArmadillo package 3,
which makes the use of the Armadillo C++ library 4 from within an R
package very straightforward.

<!-- TODO bridge these paragraphs -->

Here we introduce the fmlr package 5, a novel framework for matrix
computing with R whose primary concern is performance. It provides
numerous matrix and statistics operations for both 32 and 64-bit
floating point data, stored on CPU, GPU, or distributed across an MPI
cluster, all with a single, unified interface managed by R6 6.
Additionally, because our interface is entirely novel, we are able to
avoid some of the inherent performance penalties imposed by the R matrix
interface, including those mentioned above. If accepted, we plan to show
the UseR attendee some of the capabilities of this new framework, its
syntax, and some example performance benchmarks.

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

<div id="ref-rcpparmadillo">

\[3\] D. Eddelbuettel and C. Sanderson, “RcppArmadillo: Accelerating r
with high-performance c++ linear algebra,” *Computational Statistics &
Data Analysis*, vol. 71, pp. 1054–1063, 2014.

</div>

<div id="ref-armadillo">

\[4\] C. Sanderson and R. Curtin, “Armadillo: A template-based c++
library for linear algebra,” *Journal of Open Source Software*, vol. 1,
no. 2, p. 26, 2016.

</div>

<div id="ref-fmlr">

\[5\] D. Schmidt, *fmlr: Fused matrix library for r*. 2021.Available:
<https://hpcran.org/packages/fmlr/index.html>

</div>

<div id="ref-R6">

\[6\] W. Chang, *R6: Encapsulated classes with reference semantics*.
2021.Available: <https://CRAN.R-project.org/package=R6>

</div>

</div>
