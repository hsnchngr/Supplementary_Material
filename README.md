# Supplementary Material, Code and results

Code behind every table and figure of "Uncertainty Aware Physics Informed Digital Twins for Proactive Transient Control and Capacity Optimization in Multiband Optical Networks" (main paper and supplementary material).

Folder names are Turkish and are used as paths by the scripts: `kod` = code, `sonuclar` = results. Run every script from the project root, the folder that contains `kod`.

Environment: Python 3.13, numpy 2.3, scipy 1.16, torch 2.9 (CPU), matplotlib. GNPy 3.0.1 in a separate virtual environment is needed only for step 6.

## Pipeline

| Step | Script | What it does | Feeds |
|---|---|---|---|
| 1 | `00_download_cosmos.py`, `01_parse_cosmos.py` | Download and parse the open COSMOS EDFA dataset | all steady state results |
| 2 | `02_steady.py`, `02b_external.py` | Steady state twin, leave one device out, drift and external data | Table I, Fig. 3 |
| 3 | `03_transient_models.py` | Reference solver data, MLP, LSTM, PINN, Neural ODE, physics core, hybrid twin | Table II, Fig. 4 |
| 4 | `05_control.py all` | Single stage control runs, solver convergence, ablations | Fig. 5, Fig. S5, Tables S-I and S-V |
| 5 | `14_planner_scaling.py` | Wall time of one planner update against the number of stages | Table S-IV |
| 6 | `04a_gnpy_eta.py` | GN model matrix and Raman tilt reference from GNPy | network simulation |
| 7 | `06_network.py`, `06_network.py 8 traces` | Multispan C+L line, GSNR, margins, capacity | Table III, Figs. 6, 8, S4 |
| 8 | `10_hhi.py` | Fraunhofer HHI EDFA Dataset 01, second testbed | Table I, Fig. 3d |
| 9 | `12_hhi_spectra.py`, `11_hhi_qot.py` | Fraunhofer HHI Experimental Dataset 01, measured QoT check | Fig. 7 |
| 10 | `08_result_figs.py`, `09_network_figs.py`, `13_hhi_qot_fig.py` | All result figures and the numbers quoted in the text (`sonuclar/numbers_*.json`) | Figs. 3 to 8, S4, S5 |

Shared modules: `physics.py` (erbium model, Raman coupling), `sim.py` (twin, AGC, planner), `ctrl.py` (controller bank, line, QoT), `figstyle.py` (figure style).

## Result files

`sonuclar/*.json` hold the numbers behind the tables and the text: `numbers_a.json` (steady state, transient, control), `numbers_net.json` (network), `hhi.json` and `hhi_qot.json` (Fraunhofer HHI data), `planner_scaling.json` (planner timing). All random seeds are fixed in the scripts.

## Data

The COSMOS EDFA dataset is public (https://github.com/functions-lab/COSMOS-EDFA-Dataset). The Fraunhofer HHI datasets are available on request from Fraunhofer HHI under CC BY 4.0 (https://www.hhi.fraunhofer.de/en/networkdata.html) and are not redistributed here.
