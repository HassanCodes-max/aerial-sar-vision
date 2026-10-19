# Environment setup

Two places do different jobs:

- **Laptop (VS Code):** editing code, git, and light CPU inference with small models.
- **Kaggle or Colab GPU:** training and heavy inference.

## Laptop

1. Install Python 3.10 or newer, Git and VS Code (with the Python extension).
2. Clone the repo and create a virtual environment:

```bash
git clone https://github.com/HassanCodes-max/aerial-sar-vision.git
cd aerial-sar-vision
python -m venv .venv
# Windows:      .venv\Scripts\activate
# macOS/Linux:  source .venv/bin/activate
pip install -r requirements.txt
```

## Kaggle (primary GPU)

1. Create an account at kaggle.com and verify your phone number. As far as I know this is required before GPU and Internet can be switched on in notebooks.
2. Create a new notebook: File, Import Notebook, then upload `notebooks/00_first_contact.ipynb`.
3. In the notebook settings, choose a GPU under Accelerator and turn Internet on.
4. Run the cells from top to bottom.
5. Free GPU time is limited each week. Check the quota shown in your Kaggle notebook settings or profile.
6. Files written to `/kaggle/working` are kept only for saved versions (Save Version, then Save & Run All). Download anything you need.
7. To bring work back to the repo: File, Download Notebook, copy it into `notebooks/`, then commit and push.

## Colab (backup)

Open the notebook, choose Runtime, Change runtime type, then a GPU. Colab sessions are temporary, so save checkpoints to Google Drive.
