# PyPSA-Eur grid extraction 60-400 kV

## Extract

- Clone pypsa-eur
- Install via `conda env create -f envs/linux-64.lock.yaml` and activate
- Run: `snakemake prepare_osm_network_release -j1 --configfile config/examples/config.distribution-grid-experimental.yaml`
- Results are stored in `resources/distribution-grid-experimental/`

## Changes

See doc on Sharepoint for details

## Clip to DE:

- `custom_scripts/clip_grid.py`

## Notes on assets

- Lines
  - [Standard types in config](https://github.com/PyPSA/pypsa-eur/blob/3df3152db900730df34eca86646f4a490940d48a/config/config.default.yaml#L314-L327)
  - [Available standard types](https://docs.pypsa.org/latest/user-guide/components.html#line-types)
  - `s_nom` is inferred [here](https://github.com/PyPSA/pypsa-eur/blob/3df3152db900730df34eca86646f4a490940d48a/scripts/base_network.py#L335-L341)
- Transformers
  - [Available standard types](https://pypsa.readthedocs.io/latest/user-guide/components.html#transformer-types)
  - `s_nom` is inferred [here](https://github.com/PyPSA/pypsa-eur/blob/3df3152db900730df34eca86646f4a490940d48a/scripts/build_osm_network.py#L1203-L1212) be calculating the capacity of transformers based on the
    maximum capacity of connected buses. It can be overridden [here](https://github.com/PyPSA/pypsa-eur/blob/3df3152db900730df34eca86646f4a490940d48a/scripts/base_network.py#L409-L418).
- Standard types based upon [pandapower](https://pandapower.readthedocs.io/en/develop/std_types/basic.html)


