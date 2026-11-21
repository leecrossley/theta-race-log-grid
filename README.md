# Both prime-race moves on any one-part-per-million log grid

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24412100.svg)](https://doi.org/10.5281/zenodo.24412100)

This result is now maintained in [theta-host-split-inert-race](https://github.com/leecrossley/theta-host-split-inert-race/tree/main/results/theta-race-log-grid). This repository is archived and keeps its releases and DOI.

Pick any real $`H\ge1`$ and any offset for a geometric grid with log step $`10^{-6}`$. In the dyadic 547/727 prime-ideal race, **both a gain and a loss above $`1.9735\log2`$ in magnitude start on that grid after $`H`$ and finish by $`10^{18}H`$.** At most 40,753,385 grid starts are eligible. [Theorem and proof](PROOF.md)

The stronger statement gives two complete intervals of log starting heights, one for each direction. Each interval has width $`10^{-6}`$ and every start in it qualifies. The earlier deadline guaranteed a point for each sign. This result also applies to every finer log grid. [Earlier deadline](https://github.com/leecrossley/theta-race-filtered-deadline/blob/2400dc5ac2a7969d41e1a4bde1eb44dd6c63b7a2/PROOF.md) · [Prior work](PRIOR-WORK.md)

| Calculation | Certified result |
|---|---|
| Gamma integral and the Fourier series of the absolute sine | The full zero profile changes by less than 0.0141 under any log shift up to half the mesh. |
| Closed gamma moments grouped in 344 blocks | An independent calculation gives the stronger bound 0.0085 over the same range. |
| Actual primes at small heights | Two finite sieve rows and elementary slope bounds preserve both signs over complete intervals. |

The grid bound counts candidate heights. Evaluating the prime sum at an arbitrarily high candidate is a separate computational problem. [Verification output](evidence/check.txt) · [Exact grid lemma](LogGrid.lean)

## Replay

In a Python 3.10+ virtual environment run

```sh
python -m pip install -r requirements.txt
python modulus.py
python closed_moment.py
python heights.py
python check_source.py
```

On x86-64 Linux with Git, curl, tar and zstd, `bash verify-release.sh` checks the hashes, upstream records, two modulus calculations, finite witnesses and five local Lean deductions. With Lean 4.33.1 on PATH and a built Mathlib at commit `0df444a360eaa60ab8c11dca51a86af692955474`, run `bash verify-release.sh /path/to/mathlib4`. An optional second argument gives the directory of the five upstream records. The Fourier and explicit-formula arguments are written proofs. [File hashes](SHA256SUMS) · [Pinned deadline transcript](evidence/deadline-check.txt)
