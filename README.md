# rndttest
Perform a Randomisation test to assess difference in means.<br/>
Permutation or randomisation tests are a useful alternative to more
standard parametric tests for analysing experimental data. They have the
advantage of making no distributional assumptions (such as Normality)
about the data, while remaining as powerful as more standard tests. 
The t-test assumes that the two groups arose by drawing samples from two
Normally distributed populations, and that we are investigating whether
these populations differ in their mean. 
The randomisation test, on the other hand, assumes that some initial set
of individuals were randomly allocated to two treatment groups.
The number of permutations to be examined soon grows prohibitively large,
so, this function uses two approaches: an Exact Method when the possible
permutations are less than 20.000 and a Monte Carlo Naive Method when the
permutations are more than 20.000.

Syntax: pvalue=rndttest(x,y,delta,alpha)

Inputs: 
          X and Y (mandatory) - data vectors. 
          DELTA and ALPHA (optional)- If Monte Carlo method is used it is 
          necessary to evaluate how many times the process must be 
          reiterated to ensure that p-value is within DELTA units of the 
          true one with (1-ALPHA)*100% confidence. 
          (Default DELTA=ALPHA=0.01).

Output:    p-value

Example: 
          X=[10 11 12]; Y=[17 18 19];

          Calling on Matlab the function: rndttest(X,Y)

          Answer is:

RANDOMISATION TEST
--------------------------------------------------------------------------------
Exact Method
--------------------------------------------------------------------------------
20 randomisations evaluated
Probability (p-value) that the observed difference is accidental: 0.1000
--------------------------------------------------------------------------------

This p-value is the best one that can be quoted for these data. It is
based only on the assumption that individuals are allocated at random
to groups. It does not assume anything about Normality of
distributions, which may or may not be true. Even when such
assumptions are true, the randomisation test is as powerful as a t-test.
(If you are curious, a t-test of the experimental data in our example gives p=0.00102)

          Created by Giuseppe Cardillo
          giuseppe.cardillo-edta@poste.it

To cite this file, this would be an appropriate format:
Cardillo G. (2008) Rndttest: An alternative to Student t-test assessing difference in means.  
http://www.mathworks.com/matlabcentral/fileexchange/20928
