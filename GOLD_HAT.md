# The Gold Hat Manifesto

This repository is built under the Gold Hat principle: does this empower or extract?

The full manifesto lives in one place, so every repository points to one source of truth instead of carrying a divergent copy:

https://github.com/HermeticOrmus/gold-hat-manifesto

In short: empower the person using the tool, teach while helping, respect autonomy, build for the long term, solve root causes. When a design decision is unclear, choose the option that leaves the user more in control of their own work and their own data. When the honest answer is "extract", it does not ship.

## Apply it here (GEO)

| Empower | Extract |
|---------|---------|
| Teach the llms.txt format so the owner can update it after the next ship | A generated file they cannot explain, or a fake "AI visibility score" |
| Mark unverified claims and attach evidence | Invented statistics, "studies show", or a 0–100 citability number |
| JSON-LD that matches the visible entity | Fake `aggregateRating`, stuffed `sameAs`, awards that are not public |
| List residual risks the next pass still owns | Pretend stub skills (`geo-audit`, presence, freshness) are melted |
| Keep private paths and secrets out of machine guidance | Admin, staging, or credentialed URLs in `/llms.txt` |

If a GEO change would look good in a demo and worse for the person who has to live with the site, it is extract. Do not ship it.
