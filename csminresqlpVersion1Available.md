# Introduction #


I'm a graduate student in EE at Caltech. I was wondering if you have
Matlab code available for the complex symmetric version of your minresQLP algorithm. I noticed on your website that it says "coming soon", but I was wondering if there is anything currently available that I could try out. I am solving very large (poorly conditioned) sparse systems that arise from finite difference discretization of 3D time-harmonic Maxwell's equations. The resulting system matrices are complex symmetric, and I have been using the BiCGStab(l) algorithm thus far with mixed success. BiCGStab(l) seems to often stagnate and get stuck on larger problems, and I have to restart it with different initial conditions to achieve convergence. Thus, I really would like to evaluate the performance of CS-MINRES-QLP for my
problem.


# Details #

Thank you for your interests in CS-MINRES-QLP. I have just uploaded it to my website.

It sounds like you have a challenging problem. So please give CS-MINRES-QLP a try and let me know how it performs (even if it is not good news). I may be able to help tune the parameters.  I am also interested in hearing any kind of comments such as TYPOs or erroneous messages or documentation in both the software and the manuscript.


If you or your collaborator(s) appreciate this work, please cite the software as well as the manuscript.


I wish you all the best in your research work.