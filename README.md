# Supplementary Material, Code and results

Code behind every table and figure of "Uncertainty Aware Physics Informed Digital Twins for Proactive Transient Control and Capacity Optimization in Multiband Optical Networks" (main paper and supplementary material).

Folder names are Turkish and are used as paths by the scripts: `kod` = code, `sonuclar` = results. Run every script from the project root, the folder that contains `kod`.

Environment: Python 3.13, numpy 2.3, scipy 1.16, torch 2.9 (CPU), matplotlib. GNPy 3.0.1 in a separate virtual environment is needed only for step 6.

## Result files

`sonuclar/*.json` hold the numbers behind the tables and the text: `numbers_a.json` (steady state, transient, control), `numbers_net.json` (network), `hhi.json` and `hhi_qot.json` (Fraunhofer HHI data), `planner_scaling.json` (planner timing). All random seeds are fixed in the scripts.

## Data

The COSMOS EDFA dataset is public (https://github.com/functions-lab/COSMOS-EDFA-Dataset). The Fraunhofer HHI datasets are available on request from Fraunhofer HHI under CC BY 4.0 (https://www.hhi.fraunhofer.de/en/networkdata.html) and are not redistributed here.
