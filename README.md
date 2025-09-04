![example_raster_annotations](https://github.com/user-attachments/assets/1b3155a2-aa41-4b1a-a7a5-b18f3a3bff49)


# FYSEMR 73z - Lasers

Quickstart: Run the DINO-X detection and other notebooks

Prerequisites
- uv (recommended). Install instructions: https://docs.astral.sh/uv/getting-started/
- DDS API token (provided in class or get your own for free from https://cloud.deepdataspace.com/apply-token)

Steps
1) Clone the repository
```bash
git clone git@github.com:lukehollis/fysemr73z_lasers.git
cd fysemr73z_lasers
```

2) Create and activate a virtual environment with uv, then install dependencies
```bash
uv venv
source .venv/bin/activate
uv sync
```

3) Configure environment variables
- Copy the template and set your API token (provided in class):
```bash
cp .env.template .env
# then edit .env to set:
# DDS_API_TOKEN=<your token here>
```
- The notebook loads .env automatically via python-dotenv.

4) Open and run the notebook
- Open `DDS_DINOX_detection.ipynb` in VS Code or Jupyter, select the `.venv` Python interpreter, and run the cells (Run All).
- The notebook:
  - Reads `DDS_API_TOKEN` from `.env`
  - Calls the DDS DINO-X detection API on `./data/copan_dem_01m_raster.jpg`
  - Saves results to:
    - `outputs/dinox_result.json`
    - visualizations under `outputs/dinox/`

Troubleshooting
- uv not found: install uv from the link above, then retry steps.
- KeyError: 'DDS_API_TOKEN': ensure `.env` exists and contains a valid `DDS_API_TOKEN` value.
