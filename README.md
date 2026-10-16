[![DOI](https://img.shields.io/badge/DOI-10.82901%2Fnemar.on003078-blue)](https://doi.org/10.82901/nemar.on003078)

## Known issue: every recording holds the same signal (found 2026-10-16)

All 72 `sub-*/ieeg/*_ieeg.fdt` signal files (6 subjects x 12 runs) are one and the same file: the same git-annex key
(`MD5E-s155550720--931bf5fb80080392323c5b4eec9a0328.fdt`, 155,550,720 bytes). The 72 `.set` headers differ (72
distinct keys), the signal they point to does not. The source has the same problem: in OpenNeuro ds003078 1.0.0 the 72
`.fdt` files are also a single blob. So at most one of the 72 runs can carry its own data, and which one is not known.
Do not use these recordings as 72 distinct runs. The metadata (events, channels, electrodes, MRI) are unaffected.
Reported by Julien Gadonneix; checked against both git trees.

--- version 1.0.0 ---

initial release

Raw iEEG data + pre and post surgery MRI 
No reference to the published study (still in press)