# BipartiteSUSY

BipartiteSUSY is a Mathematica package designed to perform calculations 
for physical theories based on bipartite graphs. In particular, the 
package can employ the recently developed arsenal of techniques 
surrounding on-shell diagrams in N=4 SYM scattering amplitudes, 
including those for non-planar diagrams, with particular attention to 
computational speed. It also contains a host of tools for computations 
in N=1 Bipartite Field Theories, which utilize the same bipartite graphs.
 Through the use of an interactive graphical tool, it is possible to draw
 the desired diagrams on the screen and compute commonly sought-after 
 features. The package should be easily accessible to users with little 
 or no previous experience in dealing with bipartite graphs and their 
 combinatorial descriptions.

## Documentation

The package has a full documentation complete with installation 
instructions, full list of functions, and how to use them, at the arXiv 
preprint server. The identifier is [arXiv:1702.03949](https://arxiv.org/abs/1702.03949).

## Install

Installation of Mathematica packages is not required. To use the package 
and its functionality, simply download the `bipartiteSUSY.m` file and place
it in the [working directory](https://reference.wolfram.com/language/ref/Directory.html) of the notebook you're working in. Then, to
load the package with all its functionality, simply evaluate
```
<<bipartiteSUSY.m
```
in the first cell of the notebook.

The includion of the (unpackage) file `premadePluckerRelations.rar` in 
the same folder will speed up the computation of Plucker relations. 
More full instructions are found in the [documentation](https://arxiv.org/abs/1702.03949).

## Inventory of files

For simply using the package, the only required file is `bipartiteSUSY.m`.
Here is a list of the additional files and what they are for:
 - `.gitignore`, `LICENSE.txt` and `README.md` are files added to GitHub 
in order to use git smoothly, specify what License the package is under 
(see below), and the readme file you are currently reading.
 - `bipartiteSUSY.m` is the Mathematica package to be used.
 - `bipartiteSUSY.nb` is a notebook version of the package, which is 
much easier to read than the .m file and is the most appropriate one
in which to work when wanting to augment and improve the package.
 - `packageDevelopment.nb` is the notebook I use as a facility in which 
to develop new code. It contains a few handy examples to test new code 
on, but is by no means a requirement to use when developing the package.
 - `packageFixingFacility.nb` is the notebook I use to fix bugs, 
 usually discovered by the testing facility notebook, below.
 - `packageNEWTestingFacility.nb` contains the tests I run on the 
functions before declaring them good for usage. It is important 
to use this notebook on new code developed for the package.
 - `premadePluckerRelations.rar` contains the compressed data file 
used to speed up the computation of Plucker relations.
 - `racingmethods.nb` is a handy notebook used to race against each 
other different methods of achieving an end goal. Since the package is 
designed for speed as well as ease of use, it is very helpful to test 
small bits of code to check which way they run fastest.
 - `testingdata.rar` contains the compressed files containing the 
Kasteleyn matrices used for preliminary tests. The full tests are 
many gigabytes in size and contain millions of examples, and are 
hence not included on GitHub.

## Contributing

Contributions are very welcome and very actively encouraged, provided 
this package is quoted as the originating platform on which the 
improvements were made. Here I highlight some areas that would be 
particularly useful to contribute to:

 - It would be useful to have a function which uses `squareMove` to 
generate all square-move-equivalent phases of a diagram. This could be
used to speed up the stratification functions, which currently perform
the sub-stratification of multiple equivalent phases of a diagram.
 - Automate findind the integrand form associated to an on-shell 
diagram in N=4. Currently the fastest method known is explained in
detail in [arXiv:1502.02034](https://arxiv.org/abs/1502.02034). The challenge I identified in completely 
automating this method is that there are very many Plucker-relation-
equivalent expressions that can result from this technique; these 
depend on the choices made when creating the T-matrix and M-matrix, 
and when taking residues around poles belonging to auxiliary edges.
I did not find a satisfactory way of automating how to find the ideal, 
most concise expression for the integrand form, which has the correct 
little-group weights. However, I did not try very hard and it should 
be relatively easy to make good progress on this, since it is rather
simple to perform the copmutations by hand for each individual on-shell 
diagram.
 - Expanding on the drawGraph functionality, for example by including 
the ability to spit out the integrand form (see previous point), or 
by allowing it to perform collapse of bivalent nodes and square moves 
directly in the graph-drawing box. Another nice feature would be the 
ability to undo a certain numebr of steps, in the case of mistakes.
------------------------------------------------------------------------
Before declaring any changes to the package complete, please check that 
the changes haven't introduced bugs. This can be done by running the 
tests found in the "testing facility" notebook 
`packageNEWTestingFacility.nb`, using the Kasteleyn matrices found in 
the data files in `testingdata.rar`. Once the tests are complete, I can 
run the full set of tests, on millions of examples, to check much more 
subtle ways in which the code can fail. Once those tests are passed, the 
code can be incorporated into a new release version of the package!

## License

This Mathematica package is covered under the [Apache License 2.0](https://choosealicense.com/licenses/apache-2.0/).
