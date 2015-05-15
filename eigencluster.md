# Question #

I was looking for a reference in numerical computation and was hoping if
you could help. We are trying to solve an equation of the form _Ax = b_,
where _A_ is symmetric positive definite, using the Lanczos method and
trying to get an understanding of the number of iterations needed. We
understand that the number of iterations depends on the number of clusters of eigenvalues of the matrix _A_. I was wondering if you have reference to any article(s) which states this result rigorously.


# Details #

We could refer to the following article among others for the idiomatic property:

A. Greenbaum and Z. Strakos. Predicting the behavior of finite precision Lanczos and conjugate gradient computations. SIMAX 1992.