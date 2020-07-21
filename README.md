This repository presents results of the specialization of the word equations interpreter WECount by equations given as a benchmark for the solver Woorpje, download [here](https://www.informatik.uni-kiel.de/~mku/woorpje/files/track01.tar.gz). The description of the equations in the track is given [here](https://www.informatik.uni-kiel.de/~mku/woorpje/#_first_track).

The interpreter source code is [weqs_int_bench_task.ref](https://github.com/TonitaN/TestEquations/blob/master/weqs_int_bench_task.ref), where the input equation is to be replaced by the one to be solved.


The equations are encoded as follows.

Variables are encoded as As, Bs, ...., Xs.

Letters (constant symbols) are encoded as a, b,...,x.


Residual programs that correspond to equations with no solutions contain the single rule:

$ENTRY Go {

(e.101) =  False;

}

The other residual programs model graphs of all solutions of the corresponding equations.

The paths in graphs contain the following labels:

('Xs -> empty') --- variable Xs has the value the empty string;

('Xs -> Ys Xs') --- variable Xs has the prefix Ys;

('Xs -> a Xs') --- variable Xs starts by the letter a.

Say, given the path ('Xs -> a Xs')('Xs -> Ys Xs')('Xs -> empty') it models the solution Xs = a Ys.
