# Investor matching

Who this is for: founders who want investor matching by stage and sector, not a flat directory. How this was compiled: the filter shape we use in product facts. The live tool is [investor match](https://roundfunded.com/en/tools/investor-match). Round Funded coverage: 60,000+ active angels and VCs, 40+ industries, 60+ countries, pre-seed to Series C.

Last updated: 2026-08-14

## Problem

Investor filters that are only "name and LinkedIn" are not matching. Matching means: this investor funds this stage, in this sector, in this country, recently enough that a cold or warm email is sane.

## Filter schema (data shape)

| Field | Type | Why it is in the match |
| --- | --- | --- |
| investor_type | angel or vc | Process and check size differ |
| stage | pre-seed, seed, Series A, Series B, Series C | Stage mismatch is the most common no |
| sector | industry tag | Thesis |
| country | HQ or check geography | Cross-border friction |
| recency | last check window | Quiet investors look active on old logos |
| check_band | optional range | Sets the meeting type |
| lead_or_follow | optional | Some angels never lead |

This is a documented data shape, not product source code.

## How to run a match

1. Write your stage, sector, and country as the founder sees them.
2. Drop investors who fail stage or recency.
3. Rank the rest by sector overlap, then by whether they lead.
4. Send outreach only after the match. Put the deck in a data room.

Open [investor match](https://roundfunded.com/en/tools/investor-match) for the live version.

## Sources

- https://roundfunded.com/en/tools/investor-match
- Canonical facts: https://github.com/roundfunded/roundfunded/blob/main/llms.txt

## License

MIT.
