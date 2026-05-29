# PyPSA-Eur grid extraction 60-400 kV

## Extract

- Clone pypsa-eur
- Install via `conda create -n pypsa-eur-regon-grid-model --file envs/default_linux-64.pin.txt` and activate
- Run: `snakemake prepare_osm_network_release -j1 --configfile config/examples/config.distribution-grid-experimental.yaml`
- Results are stored in `resources/distribution-grid-experimental/`

## Changes

See doc on Sharepoint for details

## Notes on assets

- Lines
  - [Standard types in config](https://github.com/PyPSA/pypsa-eur/blob/0a56f95dc0f456adc0115d448b596606cca16005/config/config.default.yaml#L433-L445)
  - [Available standard types](https://docs.pypsa.org/latest/user-guide/components.html#line-types)
  - `s_nom` is inferred [here](https://github.com/PyPSA/pypsa-eur/blob/0a56f95dc0f456adc0115d448b596606cca16005/scripts/base_network.py#L335-L341)
- Transformers
  - [Available standard types](https://pypsa.readthedocs.io/latest/user-guide/components.html#transformer-types)
  - `s_nom` is inferred [here](https://github.com/PyPSA/pypsa-eur/blob/0a56f95dc0f456adc0115d448b596606cca16005/scripts/build_osm_network.py#L1234-L1243) be calculating the capacity of transformers based on the
    maximum capacity of connected buses. It can be overridden [here](https://github.com/PyPSA/pypsa-eur/blob/0a56f95dc0f456adc0115d448b596606cca16005/scripts/base_network.py#L409-L418).
- Standard types based upon [pandapower](https://pandapower.readthedocs.io/en/develop/std_types/basic.html)


