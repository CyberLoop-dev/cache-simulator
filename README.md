# Cache Simulator

![Status](https://img.shields.io/badge/status-early%20prototype-8b9cf7?style=flat-square) ![Runtime](https://img.shields.io/badge/runtime-browser-28a6a1?style=flat-square)

Cache Simulator makes replacement policies visible. Enter a page-reference sequence, choose a cache capacity, and inspect every hit, miss, and eviction.

## Why it exists

A final hit-rate number hides the decisions that produce it. This lab shows the trace so students can reason about FIFO and LRU one access at a time.

## Features

- Simulate FIFO and LRU replacement.
- Edit the reference sequence and cache capacity.
- Show each access, hit/miss result, and cache contents.
- Summarize hits, misses, and hit ratio.
- Run locally in one page with no external dependencies.

## Architecture

A deterministic simulator processes the reference sequence from left to right. FIFO tracks insertion order; LRU updates recency on each hit. The UI renders the trace table after the run.

~~~text
cache-simulator/
|-- README.md
|-- index.html
~~~

## Setup

Open index.html in a modern browser. No package manager or server is required.

## Quick start

Use sequence 1,2,3,1,4,1,2,5, set capacity to 3, choose FIFO, and press Simulate. Switch to LRU and compare the eviction decisions.

## Example

With a capacity of three, FIFO evicts the oldest loaded page. LRU evicts the page that has gone unused for the longest time.

## Scope

This is an educational simulation, not a measurement of a real machine's CPU or disk cache. The current implementation includes FIFO and LRU only.

## Roadmap

- [ ] Add LFU and optimal replacement for comparison.
- [ ] Add a playback control for one access at a time.
- [ ] Export a trace as CSV.

## Contributing

Issues, reproducible bug reports, documentation fixes, and focused pull requests are welcome. Keep the simulator deterministic and explain any algorithmic assumptions.

## License

No license file has been selected yet. Do not assume redistribution or reuse rights until a license is added.
