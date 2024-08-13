# TBFS

Various algorithms for computing temporal closeness in temporal graphs, and related measures.

## Install

Intall rust and then:
```
cargo build --release
```

## Shortest closeness

Computation of the harmonic closeness of all nodes:
 the harmonic closeness of `s` is `\sum_{t != s} 1 / dist(s,t)`
 where `dist(s,t)` is the length in number of temporal edges
 of a shortest walk from `s` to `t`.

Example (non-restless):
```
./target/release/tgraph data/MathOverflow.patg --command shortest-closeness
```

Example with maximum waiting time of 300 seconds (restless):
```
./target/release/tgraph data/MathOverflow.patg --command shortest-closeness --beta 300
```

## Top-k shortest closeness

Same as `shortest-closeness`, but compute only the top `kappa` values.

Example:
```
./target/release/tgraph data/MathOverflow.patg --command top-k-shortest-closeness --kappa 10 --beta 300
```


## LICENSE

GPL-3.0 license
