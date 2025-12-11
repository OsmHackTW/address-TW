### Address fixes for alleys in named lanes

In the original imports, alleys in named lanes will only have lane name in `addr:place`. This folder contains attempts to fix that.

e.g. for alley named `和平一巷2弄` (Alley 2, Heping 1st Lane):
* Before: `addr:place=和平一巷`
* Unsucessful fixes: `addr:street=和平一巷`
* After: `addr:street=和平一巷2弄`

All work in progress CSVs:
* `lane with wrong address.csv`: List of all alleys involved.
* `lane with name.csv`: All addresses needs to be imported, done by Supaplex.
* `lane with name revised.csv`: Fix wrong data in the above file, done by Littlebtc.

All the actual fixes are implemented in two OSM changesets:
* https://www.openstreetmap.org/changeset/175815246
* https://www.openstreetmap.org/changeset/175816060
