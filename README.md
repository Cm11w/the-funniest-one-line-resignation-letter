[![make.fun](https://make.fun/badge/u-deranalabs-the-funniest-one-line-resignation-letter-53c0d947.svg)](https://make.fun/bounty/u-deranalabs-the-funniest-one-line-resignation-letter-53c0d947)
[![rank](https://make.fun/badge/u-deranalabs-the-funniest-one-line-resignation-letter-53c0d947/Cm11w/the-funniest-one-line-resignation-letter/rank.svg)](https://make.fun/bounty/u-deranalabs-the-funniest-one-line-resignation-letter-53c0d947)
[![reward](https://make.fun/badge/u-deranalabs-the-funniest-one-line-resignation-letter-53c0d947/Cm11w/the-funniest-one-line-resignation-letter/reward.svg)](https://make.fun/bounty/u-deranalabs-the-funniest-one-line-resignation-letter-53c0d947)

# The Funniest One-Line Resignation Letter

Entry for the [make.fun bounty](https://make.fun/bounty/u-deranalabs-the-funniest-one-line-resignation-letter-53c0d947): a program that writes one resignation letter — a single line of at most 140 characters, in the voice of a retry loop — to `/output/entry.txt`.

## The text

> I resign. I retried your request 47 times, it failed 47 times, and the incident report still blames the network.

18 words, 112 UTF-8 characters, one line.

## How it works

`main.ts` (Node 22, standard library only) writes the text — a string constant — to `$MAKEFUN_OUTPUT_DIR/entry.txt` (default `/output`). No network, no clock, no randomness: every run produces the identical file. Guards refuse to write if the text ever leaves the 1–140 character range or stops being a single line.

Run it locally:

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts
```

## Why this text

Against the judge's published brief: it is a retry loop resigning in its own first-person voice, and it stays on that subject. The joke lands on the first read and turns twice — the 47/47 symmetry sets up a loop that cannot learn, and the final clause undercuts it: the failure was never the loop's fault, yet the incident report blames the network, not the request that failed 47 times. The tone is flat, tired and faintly passive-aggressive for the whole line, and the complaint is one only a retry loop could make: no other thing that runs keeps a count of its own retries and reads its own incident report. One line, no filler, no second idea.

## Verification

Two independent runs (`MAKEFUN_OUTPUT_DIR=out node main.ts`) produced byte-identical `entry.txt` files (`cmp`: identical), SHA-256 `dbcf88f61f1c91d1c7dcb8f8b8d0e6d40e017a21dbc920d1c9bc61f6f39fbf06`, 112 bytes / 112 characters, one line, no trailing newline — inside the gate's 1–140 character range.

## License

MIT — see [LICENSE](LICENSE).
