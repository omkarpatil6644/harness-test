# llm-accuracy-frameworks
Frameworks for testing LLM accuracy

## Prerequisites
### System requirements
- Linux
- Bash shell
- Python >=3.10
- Git (latest version)
- pip (Python package installer)

### Installation
Step 1: Create Virtual Environment (Highly Recommended)

Step 2: Download Setup Script

Clone this repository

git clone https://github.com/AGL-Innominds-Libraries-and-Tools/llm-accuracy-frameworks.git

Step 3: Change directory

cd your-repo-directory

Step 4: Make Script Executable

chmod +x setup_lm_eval.sh

Step 5: Run Setup Script (One-Time Process)

./setup_lm_eval.sh

### Usage
Running Evaluations
Basic evaluation command structure:
#### instruct models
lm_eval --model hf \
    --model_args pretrained=<model_name> \
    --tasks <task_name> \
    --apply_chat_template \
    --fewshot_as_multiturn \
    --batch_size auto \
    --output_path <json_output_path>

#### non-instruct models
lm_eval --model hf \
    --model_args pretrained=<model_name> \
    --tasks <task_name> \
    --batch_size auto \
    --output_path <json_output_path>

### Available Tasks
- leaderboard_bbh
- leaderboard_gpqa
- leaderboard_ifeval
- leaderboard_math_hard
- leaderboard_mmlu_pro
- leaderboard_musr

### Score Normalization
After running evaluations, normalize scores using scores_normalization.ipynb



# LLM Accuracy Frameworks

This repository provides scripts and utilities to automate the evaluation of large language models (LLMs) using **lm-evaluation-harness**.  
It supports evaluating both **base** and **instruct** models and aggregating results across multiple benchmarks.

---

## Prerequisites

Before starting, ensure the following are installed:

- Python 3.9+
- Git
- CUDA-compatible GPU (recommended for large models)
- `pip` and `venv`

---

## Installation

### Step 1: Create Virtual Environment (Highly Recommended)

```bash
python3 -m venv venv
source venv/bin/activate
