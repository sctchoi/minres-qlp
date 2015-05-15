# Question #

I am a postdoc at [...] university, working on some computational
chemistry methods, and come across your MINRES-QLP documentation. The
algorithm seems exactly what I need for solving some near-singular
Hermitian linear systems, with complex offset.

By complex offset, I meant that the shift input (sigma) of the matrix _A_ is a complex number, with a small, but non-zero imaginary component. Since the shift is a complex number, I presume that MINRES-QLP can handle this case? I have set the code up, and interfaced it with mine. I must remark that the code looks as though it is fantastically written and well documented - many thanks! Linking it into my code and getting it working was no trouble.


I construct a Hamiltonian (_H_), and offset it by an energy (_E = shift I_), and solve for when it equals a perturbed system as _(H-E)x = y_. When E is equal to an eigenvalue of the system, the matrix becomes singular, and you get a peak in say _<x|y>_, as you would in say a spectroscopic spectrum. From my limited running with your minresqlp package, it is not performing well (say compared to ZGESV or ZGELS) as _(H-E)_ becomes close to singular. The matrix is saved from being truly singular by the complex component in _E_, which acts to broaden the peak. The algorithm generally gets stuck, and hits the iteration limit..


# Answer #

Given _A_ Hermitian, _shift_ has to be real for (_A-shift\*I_)  to remain Hermitian.  It is unfortunate that the version-20 Fortran-90 implementation for _shift_ is not type safe.  We have been working to produce a new version that restrict shift to real and include numerous other minor updates to make the code and documentation more polished.



If the original problem is not too ill-conditioned, then in Matlab notation, the normal equation is a workaround (eye is identity, s is shift):
```
   x=minresqlp((A-conj(s)*eye(n))*(A-s*eye(n)), (A-conj(s)*eye(n))*b)
```

