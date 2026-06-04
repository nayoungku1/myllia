# 🧬 Echoes of Silenced Genes - Kaggle Competition
![Status](https://img.shields.io/badge/Status-Work_in_Progress-orange)
> A repository dedicated to developing an end-to-end solution for the [Echoes of Silenced Genes](https://www.kaggle.com/competitions/echoes-of-silenced-genes) Kaggle Competition.

> 🚧 **Work in Progress:** The model architectures and training pipelines are currently being actively experimented with. The core codebase will be uploaded soon. **Please star this repository** to stay updated on the upcoming releases! :) 

This repository contains the data preprocessing, model training, and inference pipelines for the "Echoes of Silenced Genes" Kaggle competition. Follow the instructions below to set up the environment and prepare the dataset.

## ⚙️ Installation

### 1. Clone the Repository

First, clone the project to your local machine:

```bash
git clone git@github.com:nayoungku1/myllia.git
cd myllia

```

### 2. Environment Setup (One-step Sync)

If you don't have `uv` installed, install it first:
* **Linux / MacOS**: 
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```
* **Windows**:
```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

Then, simply run the following command. It will automatically create a virtual environment, install the correct Python version, and sync all required dependencies (including `scanpy`, `scikit-learn`, etc.) based on the `uv.lock` file:

```bash
uv sync

```

To activate the environment:

```bash
source .venv/bin/activate

```

## 📊 Data Preparation

The competition dataset is required for model training. You can download the data using one of the following methods. **Using the Kaggle API is highly recommended for a seamless setup.**

### Option A: Using the Kaggle API (Recommended)

The Kaggle API allows you to download and extract the dataset directly from the command line.

**[Prerequisites: Kaggle API Setup]**

1. Log in to Kaggle and navigate to your `Settings` > `API Tokens` tab.
2. Click `Generate new API Token` to generate your API token.
3. Save it to ~/.kaggle/access_token, where the client will read it automatically, and update its permissions:
```bash
mkdir -p ~/.kaggle && echo KGAT_[your-api-key-comes-here] > ~/.kaggle/access_token && chmod 600 ~/.kaggle/access_token

```



**[Download and Extract]**

Once the API is configured, run the following commands from the project root directory:

```bash
# Create a data directory and navigate into it
mkdir -p data && cd data

# Download the competition dataset
kaggle competitions download -c echoes-of-silenced-genes

# Unzip and remove the archive
unzip echoes-of-silenced-genes.zip
rm echoes-of-silenced-genes.zip
cd ..

```

### Option B: Manual Download

If you prefer not to use the API, you can manually download the `.zip` file from the [competition data page](https://www.kaggle.com/competitions/echoes-of-silenced-genes/data). Create a `data/` folder in the project root, place the downloaded file inside, and extract its contents.

