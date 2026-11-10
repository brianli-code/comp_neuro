# Fly brain simulation and NWB/DANDI notebooks

## 1. `shiu_sugar_to_proboscis.ipynb`

Runs the Shiu et al. (2024, *Nature*) whole-brain leaky integrate-and-fire model of the *Drosophila* brain (FlyWire connectome, ~127k neurons, ~14.7M connections) and uses it as a fixed reservoir for decoding experiments.

| Section | What it does | Result |
|---|---|---|
| 1 | Reproduce the paper's headline: sugar GRNs at 100 Hz drive proboscis motor neuron MN9 | MN9 at 69 Hz vs. authors' 67 Hz |
| 2 | Inject one-hot character codes into 500 random central-brain neurons, 100 ms, ridge readout on spike counts | 99.6 % accuracy from downstream neurons |
| 3 | Degree-preserving shuffled-connectome control | Shuffled network decodes *better* per neuron; wiring spreads activity, shuffle concentrates it |
| 4 | Render letter glyphs onto 1,307 right-eye R1-6 photoreceptors ("the fly reads text") | 93.1 % accuracy; errors are visually similar letters (B/P/R, E/F); nothing reaches the central brain in 100 ms |

## 2. `nwb_dandi_intro.ipynb`

- **NWB** (Neurodata Without Borders): an HDF5-based file format where data and the metadata needed to read it live in the same file (`subject`, `electrodes`, `trials`, `units`, `TimeSeries`).
- **DANDI**: the public archive that hosts NWB files as versioned Dandisets on S3.

The notebook streams a mouse motor-cortex recording (Dandiset 000006) straight from the archive without downloading it, reads the `trials` and `units` tables into pandas, plots a trial-aligned spike raster, then writes and validates a toy NWB file from scratch.

**Requirements:** `pynwb dandi remfile h5py`. Designed for Google Colab.