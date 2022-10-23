DeepLog is an inductive logic programming (ILP) system based on meta-interpretive learning. If you use DeepLog for research, please use this citation and cite the relevant paper.

Using DeepLog
DeepLog is written in Prolog and runs with SWI-Prolog. It uses a standard library of Prolog background knowledge (lib_dl) together
with examples to produce a new Prolog program.

The following code for 'par3' demonstrates learning the great-grandparent relation given the parent relation as background knowledge:

```
:- [lib_dl].		% Common background knowledge

pos([
	par3(sally,bob)
]).
neg([]).
```

This code can be given to DeepLog under Linux as follows.

```
$ dl par3
```

This produce the following output.

```
par3(X,Y) :- parent(X,Z), par3_1(Z,Y).

par3_1(X,Y) :- parent(X,Z), parent(Z,Y).
```

In this program the predicate symbol par3_1 is invented (i.e. does not appear in the background knowledge nor in the examples).
