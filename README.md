# cora_map_tutorial
Here is a short introduction to working with sky maps produced by cora.

1. If you're new to 21cm cosmology, read sections 1 and 2.4 of https://arxiv.org/abs/1907.08211, to set up some context.
2. If you're new to healpix, read about it at https://healpix.jpl.nasa.gov/healpixBackgroundPurpose.shtml. (Optionally, for more details, see the https://healpix.jpl.nasa.gov/pdf/intro.pdf.)
3. Install `healpy` into a new Python virtual environment on your computer, and go through the tutorial: https://healpy.readthedocs.io/en/latest/tutorial.html.
  - If on Windows, you'll need to use Windows Subsystem for Linux, because the underlying healpix library is not compatible with Windows.
  - If you're new to Python virtual environments, learn about them now. It's best practice to create a new virtual environment for each research project and never do any work outside of this environment, to avoid package conflicts and unwanted alterations to your Python setup.
4. Install `cora` (https://github.com/radiocosmology/cora) and `draco` (https://github.com/radiocosmology/draco) into your virtual environment. A convenient way to do this is to use the `mkchimeenv` script (https://github.com/chime-experiment/mkchimeenv), or you could clone `cora` and `draco` from their repositories and pip-install them from source (`pip install -e .` from within the directory for each package).
5. From the command-line, run
```
cora-makesky 21cm --nside=128 --freq 400. 500. 5 --freq-mode centre --pol full --filename maps/map_21cm.h5
```
to use cora to generate a sample set of simulated 21cm sky maps.
6. Work through `cora_map_tutorial.ipynb` to get experience with plotting these maps and measuring their power spectra.