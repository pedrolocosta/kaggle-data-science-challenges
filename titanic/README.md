# Titanic challenge environment

Run these commands in PowerShell from this `titanic` folder.

## 1. Create the environment

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\python.exe -m pip install --upgrade pip
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

The `.venv` folder contains this project's Python and packages. Using its Python
executable directly works without activating the environment.

Included packages:

- NumPy and pandas: numerical work and CSV data analysis.
- Matplotlib and seaborn: charts and exploratory analysis.
- scikit-learn: preprocessing, model training, and evaluation.
- JupyterLab and ipykernel: interactive Python notebooks.

## 2. Start working

```powershell
.\.venv\Scripts\python.exe -m jupyterlab
```

Open `notebooks` in JupyterLab and create a Python notebook. To stop JupyterLab,
press Ctrl+C in its terminal.

If using VS Code, select `.venv\Scripts\python.exe` as your Python interpreter
and notebook kernel.

Optional activation for shorter commands:

```powershell
.\.venv\Scripts\Activate.ps1
python -m jupyterlab
# When finished:
deactivate
```

If PowerShell blocks activation, use the full executable path shown above.

## 3. Add the competition data

Download and extract the Titanic competition data into `data`:

```text
titanic/
  .venv/
  data/
    train.csv
    test.csv
    gender_submission.csv
  notebooks/
  requirements.txt
```

The data and environment folders are ignored by Git.

In a notebook saved inside `notebooks`, load the data with:

```python
from pathlib import Path
import pandas as pd

data_dir = Path("../data")
train = pd.read_csv(data_dir / "train.csv")
test = pd.read_csv(data_dir / "test.csv")
train.head()
```

If your notebook is saved in the project root, use `Path("data")` instead.

## References

- [Python virtual environments](https://docs.python.org/3.12/library/venv.html)
- [Installing scikit-learn](https://scikit-learn.org/stable/install.html)
- [Installing JupyterLab](https://jupyter.org/install)
