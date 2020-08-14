This repository presents results of the specialization of the word equations
interpreter WECount by equations given as a benchmark for the solver Woorpje,
download [here][track01.tar.gz].
The description of the equations in the track is given [here][_first_track].

The results of specialization of equation systems given in Track 5 are presented [here][_5TrackMe]; the readme file is given [here][_5ReadMe].

The interpreter source code is [weqs_int_bench_task.ref](weqs_int_bench_task.ref),
where the input equation is to be replaced by the one to be solved.

The equations are encoded as follows.

+ Variables are encoded as `As`, `Bs`, ...., `Xs`.
+ Letters (constant symbols) are encoded as `a`, `b`,...,`x`.

Residual programs that correspond to equations with no solutions contain
the single rule:

```
$ENTRY Go {
  (e.101) = False;
}
```

The other residual programs model graphs of all solutions of the corresponding
equations.

The paths in graphs contain the following labels:

+ `('Xs -> empty')` &mdash; variable `Xs` has the value the empty string;
+ `('Xs -> Ys Xs')` &mdash; variable `Xs` has the prefix `Ys`;
+ `('Xs -> a Xs')` &mdash; variable `Xs` starts by the letter `a`.

Say, given the path `('Xs -> a Xs')('Xs -> Ys Xs')('Xs -> empty')` it models
the solution `Xs = a Ys`.

The overall results of the verification are given in the table below.
If __'Has Solutions'__ is '!' then the equation is solvable but the timeout
occurred.

__Solutions type__ is 0 if the solutions are unions of patterns (the solution
graph is a tree); is 'regular' if the solution graph contains loops, but these
loops generate regular expressions; and is 'non-regular' if the solution graph
contains some other loops.

All the equations are classified in their reduced form. E.g. the equation
`As Bs = As As` counts as acyclic, because the two occurrences of `As` are
reduced.

Acyclic equations which are not quadratic have the sides with the empty
intersection of the variables and are linear with respect to one side.

For example, the equation `As As As = Bs a Cs` is acyclic, however it
is not quadratic.

Equation Id   | Acyclic | Quadratic | 1-Variable | Solved | Has Solutions | Solutions Type |
--------------|---------|-----------|------------|--------|---------------|----------------|
Equation 1    |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 2    |    -    |     -     |      -     |    +   |       +       |    regular     |
Equation 3    |    -    |     -     |      -     |    +   |       +       |    regular     |
Equation 4    |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 5    |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 6    |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 7    |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 8    |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 9    |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 10   |    +    |     +     |      -     |    !   |       ?       |       ?        |
Equation 11   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 12   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 13   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 14   |    -    |     +     |      -     |    +   |       +       |   non-regular  |
Equation 15   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 16   |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 17   |    -    |     +     |      -     |    +   |       +       |   non-regular  |
Equation 18   |    +    |     -     |      -     |    +   |       +       |       0        |
Equation 19   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 20   |    -    |     -     |      +     |    +   |       +       |       0        |
Equation 21   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 22   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 23   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 24   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 25   |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 26   |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 27   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 28   |    +    |     -     |      -     |    +   |       +       |       0        |
Equation 29   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 30   |    -    |     -     |      -     |    +   |       +       |    regular     |
Equation 31   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 32   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 33   |    +    |     +     |      -     |    !   |       ?       |       ?        |
Equation 34   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 35   |    +    |     +     |      -     |    !   |       ?       |       ?        |
Equation 36   |    -    |     +     |      -     |    +   |       +       |   non-regular  |
Equation 37   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 38   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 39   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 40   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 41   |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 42   |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 43   |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 44   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 45   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 46   |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 47   |    +    |     -     |      -     |    +   |       +       |       0        |
Equation 48   |    +    |     -     |      -     |    +   |       +       |       0        |
Equation 49   |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 50   |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 51   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 52   |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 53   |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 54   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 55   |    -    |     -     |      -     |    +   |       +       |    regular     |
Equation 56   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 57   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 58   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 59   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 60   |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 61   |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 62   |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 63   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 64   |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 65   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 66   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 67   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 68   |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 69   |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 70   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 71   |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 72   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 73   |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 74   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 75   |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 76   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 77   |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 78   |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 79   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 80   |    -    |     -     |      -     |    +   |       +       |   non-regular  |
Equation 81   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 82   |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 83   |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 84   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 85   |    +    |     -     |      -     |    +   |       +       |       0        |
Equation 86   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 87   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 88   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 89   |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 90   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 91   |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 92   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 93   |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 94   |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 95   |    -    |     +     |      -     |    +   |       +       |   non-regular  |
Equation 96   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 97   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 98   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 99   |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 100  |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 101  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 102  |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 103  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 104  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 105  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 106  |    +    |     -     |      -     |    +   |       +       |       0        |
Equation 107  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 108  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 109  |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 110  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 111  |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 112  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 113  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 114  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 115  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 116  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 117  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 118  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 119  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 120  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 121  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 122  |    +    |     -     |      -     |    +   |       +       |       0        |
Equation 123  |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 124  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 125  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 126  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 127  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 128  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 129  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 130  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 131  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 132  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 133  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 134  |    +    |     -     |      -     |    +   |       +       |       0        |
Equation 135  |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 136  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 137  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 138  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 139  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 140  |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 141  |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 142  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 143  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 144  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 145  |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 146  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 147  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 148  |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 149  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 150  |    -    |     -     |      -     |    +   |       +       |   non-regular  |
Equation 151  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 152  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 153  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 154  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 155  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 156  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 157  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 158  |    -    |     -     |      +     |    +   |       +       |       0        |
Equation 159  |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 160  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 161  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 162  |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 163  |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 164  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 165  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 166  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 167  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 168  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 169  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 170  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 171  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 172  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 173  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 174  |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 175  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 176  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 177  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 178  |    +    |     -     |      -     |    +   |       +       |       0        |
Equation 179  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 180  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 181  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 182  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 183  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 184  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 185  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 186  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 187  |    -    |     -     |      -     |    +   |       +       |    regular     |
Equation 188  |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 189  |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 190  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 191  |    -    |     -     |      -     |    +   |       +       |       0        |
Equation 192  |    +    |     +     |      +     |    +   |       +       |       0        |
Equation 193  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 194  |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 195  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 196  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 197  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 198  |    +    |     +     |      -     |    +   |       +       |       0        |
Equation 199  |    -    |     -     |      -     |    -   |       ?       |       ?        |
Equation 200  |    +    |     +     |      -     |    +   |       +       |       0        |

[track01.tar.gz]: https://www.informatik.uni-kiel.de/~mku/woorpje/files/track01.tar.gz
[_first_track]: https://www.informatik.uni-kiel.de/~mku/woorpje/#_first_track
[_5TrackMe]: https://github.com/TonitaN/TestEquations/tree/master/Track5
[_5ReadMe]: https://github.com/TonitaN/TestEquations/blob/master/Track5/README.md