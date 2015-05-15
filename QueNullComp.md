# Question #

I have got a question on your PhD thesis.

You mention a method to compute null space vectors of a symmetric matrix
in your PhD thesis (Section 1.1.3), namely applying Krylov subspace
methods with a random right-hand side. Does this method have a proper
name?

Later, in 5.2, you call this 'inverse iteration'. Can you explain that
connection?

Furthermore, I would be very grateful if you could comment on a similar
method, which curiously seems to be merely numerical folklore. You suggest to start the Krylov method with random right-hand side, so that the residual eventually contains a nullspace vector of the (symmetric) matrix. Why don't consider the other way around, namely, starting the Krylov method with a random starting vector and zero right-hand side? The output solution then is a kernel vector, and this method seems to work in simple numerical experiments. Unfortunately, nobody at my institute could tell me more about this, but maybe you, as an expert, have more knowledge on this.


# Answer #
It is a shame we didn't think of a better proper name for the method we label as "inverse iteration" approach. The reason we associated it with inverse iteration is because the vectors x\_k eventually explode in some later iterations (see Figure 1 left-hand-side subplots). However, in the thesis, we were actually trying to make the point that the "least-squares approach" is preferred (see Figure 1 right-hand-side subplots) to the "inverse iteration" approach as the former takes less iterations to get a similarly good null vector.


The reason we didn't start with b = 0 is because the Krylov methods we used will return the pseudoinverse solution x=0 in such a case.