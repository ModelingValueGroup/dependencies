# dependencies
This repository is used to register reverse dependencies between projects.
It contains ".trigger" files that indicate that one of our repos should be rebuild whenever a package snapshot is put in the package repository.

This only applies to non-master branches because everything in produced from the master branch is properly versioned and will never ever be regenerated.
Since we use _branch-based-building_ producing snapshots new versions can be put in the package repo for other then *master* branches.
The gradle mvg plugin will take care that the github projects depending on a newly produced package will be retriggered for action-building.
This way we always keep a consistent build state.
