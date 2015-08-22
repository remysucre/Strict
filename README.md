[**Genesis**](https://github.com/remysucre/Genesis) the main software to automate haskell strictness annotation. 
It also provides tools for running experiments with Genetic Algorithm

[**Thunk leak zoo**](https://github.com/remysucre/haskell-thunk-leak-zoo) a collection of thunk leak programs
caused by laziness, together with analysis and treatments. 

[**Experiment**](https://github.com/remysucre/strict-experiments) data and notes of all relevant experiments

[**Inbox**](https://github.com/remysucre/repo-inbox) uncategorized programs/data

[**comp150-FP**](https://github.com/remysucre/comp150-FP) forked repo of the original strictness project. 
[**Wiki**](https://github.com/remysucre/comp150-FP/wiki) has important notes! 

**notes summer 2015**

The project aims to automate the task of adding strictness annotation to haskell programs, while gaining a better understanding of the effect of strictness/laziness on the performance of haskell programs. 

Our strategy and goals are: 

- first work on small and trivial programs to gain insight about genetic algorithm and strictness
- then aim to optimize medium-sized projects
- the ultimate goal is to optimize real programs and improve its performance
- a more ambitious goal is to reproduce the strictness annotation by experts

we are still at the first stage and transfering to the second. 

Genesis contains the optimizing program under construction, as well as experiment tools for tuning the algorithm. Genesis has good modularity and takes advantage of existing libraries. Strictness editing (rewrite source) is done by `Uniplate` with Generic programming; a combination of `criterion` and command-line `cabal` builds and profiles target source; and `GA` exports a light-weight genetic algorithm for evolving better performance. 

Yet Genesis is still primitive: it only accepts projects with one source file and does not take input; it relies on IO and shell scripts; optimization of any non-trivial program is infeasible. To make Genesis a serious software, we plan to: 

1. trim down the search space, using static analysis/profiling technics
2. based on experiments, fine tune the parameters to Genetic Algorithm
3. compile and profile genes purely
4. add parallelism
5. change from time-profiling to space-profiling
6. combine genetic algorithm with other algorithms

Experiments have been performed to evaluate the effectness of Genesis and to seek an optimal configuration to Genetic Algorithm. So far we know that: 

1. population and number of generation both affect gene coverage linearly
2. average score grows **aymptotically** as population or number of generation increases
3. we have data comparing genetic algorithm to a full-search

We have also built tools to obtain target projects which can serve as benchmark or expert examples. [StrictApps](https://github.com/remysucre/repo-inbox/tree/master/benchmark) searches the Hackage database for applicatoins with and without strictness annotation. 

Although we are able to obtain a large amount of sample source, we have not found a generic way to build and profile them. 

**valuable ideas**
- simulated annealing
- call-by-need calculus
- artificial neuro-network
- simulated quantum state collapse

**learn you more haskell for greater good**
- typeclasses
- GADT
- F-algebra
- fix point
- haddock
- literate haskell
- unit testing

**extraneous thoughts**

**TODO**

- [ ] add to learn
- [ ] add ideas
- [ ] process 150-FP wiki
- [ ] organize experiment data
- [ ] integrate old todo and README
- [ ] add citations
- [ ] add next steps
