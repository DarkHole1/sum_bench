## Binary string sum benchmark

To test algos use:

```sh
$ dub run --compiler=ldc2 --build=release -- --checks
```

## Results (10.10.2021)

```sh
$ dub run --compiler=ldc2 --build=release

══════════════════════════════════════════════
max string length: 100
iterations:        100000
┌──────────────────────┬───────────┬─────────┐
│         Name         │    Abs    │   Rel   │
├──────────────────────┼───────────┼─────────┤
│ unrolled chunks 16   │   10.93ms │    100% │
├──────────────────────┼───────────┼─────────┤
│ unrolled chunks 64   │   10.96ms │    100% │
├──────────────────────┼───────────┼─────────┤
│ unrolled chunks 2    │   11.08ms │    101% │
├──────────────────────┼───────────┼─────────┤
│ Dark Hole 2          │   11.28ms │    103% │
├──────────────────────┼───────────┼─────────┤
│ basic2               │   11.29ms │    103% │
├──────────────────────┼───────────┼─────────┤
│ SIMD convert         │   12.49ms │    114% │
├──────────────────────┼───────────┼─────────┤
│ stackoverflow        │   17.58ms │    160% │
├──────────────────────┼───────────┼─────────┤
│ Dark Hole            │   20.45ms │    187% │
├──────────────────────┼───────────┼─────────┤
│ basic                │  513.10ms │   4693% │
└──────────────────────┴───────────┴─────────┘

══════════════════════════════════════════════
max string length: 1000
iterations:        10000
┌──────────────────────┬───────────┬─────────┐
│         Name         │    Abs    │   Rel   │
├──────────────────────┼───────────┼─────────┤
│ unrolled chunks 64   │    4.24ms │    100% │
├──────────────────────┼───────────┼─────────┤
│ unrolled chunks 16   │    4.34ms │    102% │
├──────────────────────┼───────────┼─────────┤
│ unrolled chunks 2    │    4.48ms │    105% │
├──────────────────────┼───────────┼─────────┤
│ SIMD convert         │    4.86ms │    114% │
├──────────────────────┼───────────┼─────────┤
│ basic2               │    4.96ms │    117% │
├──────────────────────┼───────────┼─────────┤
│ Dark Hole 2          │    5.23ms │    123% │
├──────────────────────┼───────────┼─────────┤
│ stackoverflow        │   11.75ms │    277% │
├──────────────────────┼───────────┼─────────┤
│ Dark Hole            │   13.46ms │    317% │
├──────────────────────┼───────────┼─────────┤
│ basic                │  702.63ms │  16571% │
└──────────────────────┴───────────┴─────────┘

══════════════════════════════════════════════
max string length: 10000
iterations:        1000
┌──────────────────────┬───────────┬─────────┐
│         Name         │    Abs    │   Rel   │
├──────────────────────┼───────────┼─────────┤
│ unrolled chunks 16   │    3.69ms │    100% │
├──────────────────────┼───────────┼─────────┤
│ unrolled chunks 64   │    3.85ms │    104% │
├──────────────────────┼───────────┼─────────┤
│ unrolled chunks 2    │    4.17ms │    112% │
├──────────────────────┼───────────┼─────────┤
│ basic2               │    4.40ms │    118% │
├──────────────────────┼───────────┼─────────┤
│ SIMD convert         │    4.41ms │    119% │
├──────────────────────┼───────────┼─────────┤
│ Dark Hole 2          │    4.69ms │    127% │
├──────────────────────┼───────────┼─────────┤
│ stackoverflow        │   11.27ms │    305% │
├──────────────────────┼───────────┼─────────┤
│ Dark Hole            │   13.54ms │    366% │
├──────────────────────┼───────────┼─────────┤
│ basic                │ 2791.12ms │  75537% │
└──────────────────────┴───────────┴─────────┘
```
