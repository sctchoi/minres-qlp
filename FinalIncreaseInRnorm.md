# Question #

The Matlab script "`testmhd3200b.m`" shows the input and summarizes in comments what happened with `rtol = 1e-8` and `1e-12` (with `maxxnorm = 1e+8` both times). In more detail, for the second case we have

```
   b1   = ones(n,1);
   maxxnorm = 1e+8;
   rtol = 1e-12;
   x2   = minresQLP(A,b1,rtol,maxit,M,shift,maxxnorm,acondlim,trancond);
```

and the log begins and ends with

```
Enter minresQLP.  Min-length solution of symmetric (A-sI)x = b or min ||(A-sI)x - b||
n      =   3200   ||b||    = 5.657e+01   shift    = 0.000e+00   rtol     = 1.000e-12
maxit  =   1000   maxxnorm = 1.000e+08   Acondlim = 1.000e+15   TranCond = 1.000e+08
precon =      0

 ...

   iter     rnorm     Arnorm   Compatible     LS        Anorm      Acond      xnorm
     799   2.43e+01   3.89e-02   4.69e-09   2.82e-05   5.66e+01   1.54e+08   9.15e+07
     809   2.43e+01   1.54e-02   4.48e-09   1.12e-05   5.66e+01   1.94e+08   9.59e+07
     816   3.84e+01   4.76e+00D  2.72e-07   2.19e-03D  5.66e+01   1.98e+08   2.49e+06

Exit minresQLP.   flag  =      6   xnorm has exceeded maxxnorm                            
Exit minresQLP.   iter  =    816   (MINRES     -1, MINRES-QLP    817)
Exit minresQLP.   rnorm =  3.8381e+01     rnorm  direct =  3.8381e+01
Exit minresQLP.                           Arnorm direct =  4.7641e+00
Exit minresQLP.   xnorm =  2.4941e+06     xnorm  direct =  2.4941e+06
Exit minresQLP.   Anorm =  5.6600e+01     Acond         =  1.9813e+08
```

As commented in the Matlab script, the final increase in `rnorm` is what seems to imply a bug.




# Answer #

Normally `rnorm` is monotonically nonincreasing in MINRES-QLP. However, in the last iteration of MINRES-QLP, an increase in `rnorm` is not a bug if there is a decrease in `xnorm` (see last column in the log). It is a regularization feature of MINRES-QLP.