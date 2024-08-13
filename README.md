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
./target/release/tgraph graphs/mathoverflow.patg --command shortest-closeness
```

Example with maximum waiting time of 300 seconds (restless):
```
./target/release/tgraph graphs/mathoverflow.patg --command shortest-closeness --beta 300
```

## Top-k shortest closeness

Same as `shortest-closeness`, but compute only the top `kappa` values.

Example:
```
./target/release/tgraph graphs/mathoverflow.patg --command top-k-shortest-closeness --kappa 10
```

## Dataset

Directory `graphs` contains temporal graphs from [Stanford SNAP](https://snap.stanford.edu/data/) (`mathoverflow`, `super_user`, `ask_ubuntu`), [Konect](http://konect.cc/) (`topology`), [Network Repository](https://networkrepository.com/) (`slashdot_reply`, `digg_reply`, `facebook_wall`, `SMS`), [A collection of public transport network data sets for 25 cities](https://zenodo.org/records/1186215) (all cities), [tgcloseness](https://gitlab.com/tgpublic/tgcloseness/) (`arxiv`, `flickrsg`, `wiki_talk_nl`, `wikipediasg`, `prospea`), [Sociopatterns](http://www.sociopatterns.org/datasets/) (`infectious`).

## LICENSE

GPL-3.0 license
