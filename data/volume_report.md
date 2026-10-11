# Review volume report

Run time UTC: 2026-10-10T21:19:52Z

Window: 2026-07-12T21:19:52Z through 2026-10-10T21:19:52Z, inclusive.

Total rows before cap: 46454

Total rows after cap: 46454

Cap: 50000; sampling seed: 42.

Counts before cap are unique, nonempty reviews retrieved from the configured locales. They are not the total universe of store reviews: feeds can stop before the window is covered. Country is populated only for iOS and records the first storefront that returned a review, not reviewer residence. Android country is empty; store_lang records the first Play language stream that returned each review.

## By platform

| Platform | Before cap | After cap |
| --- | --- | --- |
| android | 45492 | 45492 |
| ios | 962 | 962 |

## iOS by storefront

| Storefront | Before cap | After cap |
| --- | --- | --- |
| ae | 10 | 10 |
| au | 15 | 15 |
| br | 32 | 32 |
| ca | 69 | 69 |
| de | 38 | 38 |
| es | 11 | 11 |
| fr | 42 | 42 |
| gb | 97 | 97 |
| id | 2 | 2 |
| in | 37 | 37 |
| jp | 74 | 74 |
| mx | 35 | 35 |
| us | 500 | 500 |

## Android by store_lang

| Store language | Before cap | After cap |
| --- | --- | --- |
| ar | 575 | 575 |
| bg | 3 | 3 |
| ca | 3 | 3 |
| cs | 7 | 7 |
| de | 369 | 369 |
| el | 17 | 17 |
| en | 29889 | 29889 |
| es | 5855 | 5855 |
| fa | 8 | 8 |
| fi | 2 | 2 |
| fr | 1452 | 1452 |
| hi | 36 | 36 |
| hr | 3 | 3 |
| hu | 12 | 12 |
| id | 349 | 349 |
| it | 619 | 619 |
| iw | 4 | 4 |
| ja | 319 | 319 |
| ko | 5 | 5 |
| ms | 32 | 32 |
| nb | 1 | 1 |
| nl | 84 | 84 |
| pl | 28 | 28 |
| pt | 5576 | 5576 |
| ro | 34 | 34 |
| ru | 29 | 29 |
| sk | 2 | 2 |
| sr | 3 | 3 |
| sv | 33 | 33 |
| th | 1 | 1 |
| tr | 97 | 97 |
| uk | 8 | 8 |
| ur | 3 | 3 |
| vi | 6 | 6 |
| zh-CN | 11 | 11 |
| zh-TW | 17 | 17 |

## By UTC week (Monday start)

| Week starting | Before cap | After cap |
| --- | --- | --- |
| 2026-07-06 | 40 | 40 |
| 2026-07-13 | 3709 | 3709 |
| 2026-07-20 | 3565 | 3565 |
| 2026-07-27 | 3670 | 3670 |
| 2026-08-03 | 3575 | 3575 |
| 2026-08-10 | 3817 | 3817 |
| 2026-08-17 | 3666 | 3666 |
| 2026-08-24 | 3411 | 3411 |
| 2026-08-31 | 3702 | 3702 |
| 2026-09-07 | 3706 | 3706 |
| 2026-09-14 | 3519 | 3519 |
| 2026-09-21 | 3624 | 3624 |
| 2026-09-28 | 3866 | 3866 |
| 2026-10-05 | 2584 | 2584 |

## By star rating per platform

| Platform | Stars | Before cap | After cap |
| --- | --- | --- | --- |
| android | 1 | 2588 | 2588 |
| android | 2 | 862 | 862 |
| android | 3 | 2259 | 2259 |
| android | 4 | 5642 | 5642 |
| android | 5 | 34141 | 34141 |
| ios | 1 | 510 | 510 |
| ios | 2 | 126 | 126 |
| ios | 3 | 81 | 81 |
| ios | 4 | 42 | 42 |
| ios | 5 | 203 | 203 |

## Review text lengths and shares

Lengths count Unicode characters in the unmodified body. Words use whitespace splitting; this is not language-aware tokenization. P90 uses linear interpolation.

| Dataset | Platform | Rows | Median chars | P90 chars | Under 4 words | Non-ASCII |
| --- | --- | --- | --- | --- | --- | --- |
| Before cap | all | 46454 | 16.0 | 104.0 | 54.14% | 23.57% |
| Before cap | android | 45492 | 16.0 | 97.0 | 54.94% | 22.77% |
| Before cap | ios | 962 | 122.5 | 385.0 | 15.90% | 61.75% |
| After cap | all | 46454 | 16.0 | 104.0 | 54.14% | 23.57% |
| After cap | android | 45492 | 16.0 | 97.0 | 54.94% | 22.77% |
| After cap | ios | 962 | 122.5 | 385.0 | 15.90% | 61.75% |

## Date ranges

| Dataset | Platform | Earliest date | Latest date |
| --- | --- | --- | --- |
| Before cap | android | 2026-07-12 | 2026-10-09 |
| Before cap | ios | 2026-07-12 | 2026-10-09 |
| After cap | android | 2026-07-12 | 2026-10-09 |
| After cap | ios | 2026-07-12 | 2026-10-09 |

Hours between run time and newest review (before cap): android: 24.03 hours; ios: 40.25 hours.

## Google Play language contributions (before cap)

| Language | Pages served | Rows fetched | In-window rows | Unique added | Overlapping IDs by first language | Same IDs as | Stop reason |
| --- | --- | --- | --- | --- | --- | --- | --- |
| en | 151 | 30200 | 29889 | 29889 | — | — | window_edge |
| es | 31 | 6200 | 5855 | 5855 | — | — | window_edge |
| pt | 29 | 5800 | 5576 | 5576 | — | — | window_edge |
| fr | 9 | 1800 | 1452 | 1452 | — | — | window_edge |
| ar | 4 | 800 | 575 | 575 | — | — | window_edge |
| id | 3 | 600 | 349 | 349 | — | — | window_edge |
| ru | 2 | 400 | 29 | 29 | — | — | window_edge |
| de | 3 | 600 | 369 | 369 | — | — | window_edge |
| ko | 2 | 400 | 5 | 5 | — | — | window_edge |
| it | 5 | 1000 | 619 | 619 | — | — | window_edge |
| th | 2 | 400 | 1 | 1 | — | — | window_edge |
| vi | 2 | 400 | 6 | 6 | — | — | window_edge |
| tr | 2 | 400 | 97 | 97 | — | — | window_edge |
| ja | 3 | 600 | 319 | 319 | — | — | window_edge |
| hi | 2 | 400 | 36 | 36 | — | — | window_edge |
| nl | 2 | 400 | 84 | 84 | — | — | window_edge |
| pl | 2 | 400 | 28 | 28 | — | — | window_edge |
| sv | 2 | 400 | 33 | 33 | — | — | window_edge |
| da | 1 | 47 | 0 | 0 | — | — | window_edge |
| nb | 1 | 90 | 1 | 1 | — | — | no_continuation |
| fi | 1 | 52 | 2 | 2 | — | — | no_continuation |
| cs | 2 | 400 | 7 | 7 | — | — | window_edge |
| el | 2 | 400 | 17 | 17 | — | — | window_edge |
| hu | 2 | 400 | 12 | 12 | — | — | window_edge |
| ro | 2 | 400 | 34 | 34 | — | — | window_edge |
| uk | 1 | 141 | 8 | 8 | — | — | no_continuation |
| bg | 1 | 155 | 3 | 3 | — | — | no_continuation |
| hr | 1 | 50 | 3 | 3 | — | — | no_continuation |
| sk | 1 | 31 | 2 | 2 | — | — | no_continuation |
| sr | 1 | 44 | 3 | 3 | — | — | no_continuation |
| iw | 1 | 105 | 4 | 4 | — | — | no_continuation |
| fa | 1 | 173 | 8 | 8 | — | — | no_continuation |
| ur | 1 | 25 | 3 | 3 | — | — | no_continuation |
| bn | 1 | 26 | 0 | 0 | — | — | window_edge |
| ta | 1 | 31 | 0 | 0 | — | — | window_edge |
| te | 1 | 13 | 0 | 0 | — | — | window_edge |
| mr | 1 | 41 | 0 | 0 | — | — | window_edge |
| ms | 2 | 400 | 32 | 32 | — | — | window_edge |
| fil | 1 | 18 | 0 | 0 | — | — | window_edge |
| zh-TW | 2 | 400 | 17 | 17 | — | — | window_edge |
| zh-CN | 2 | 397 | 11 | 11 | — | — | window_edge |
| ca | 1 | 70 | 3 | 3 | — | — | no_continuation |

## App Store pages served per storefront (before cap)

| Storefront | Pages served | Rows fetched | In-window rows | Unique added | Stop reason | Rejected page |
| --- | --- | --- | --- | --- | --- | --- |
| us | 10 | 500 | 500 | 500 | page_limit_http_400 | 11 |
| gb | 3 | 150 | 97 | 97 | window_edge | — |
| in | 2 | 100 | 37 | 37 | window_edge | — |
| ca | 3 | 150 | 69 | 69 | window_edge | — |
| au | 2 | 100 | 15 | 15 | window_edge | — |
| de | 2 | 100 | 38 | 38 | window_edge | — |
| fr | 2 | 100 | 42 | 42 | window_edge | — |
| es | 2 | 100 | 11 | 11 | window_edge | — |
| br | 2 | 100 | 32 | 32 | window_edge | — |
| mx | 2 | 100 | 35 | 35 | window_edge | — |
| jp | 3 | 150 | 74 | 74 | window_edge | — |
| kr | 1 | 50 | 0 | 0 | window_edge | — |
| id | 2 | 100 | 2 | 2 | window_edge | — |
| sg | 1 | 50 | 0 | 0 | window_edge | — |
| ae | 2 | 100 | 10 | 10 | window_edge | — |

## Locales with no in-window reviews

play: da, play: bn, play: ta, play: te, play: mr, play: fil, appstore: kr, appstore: sg
