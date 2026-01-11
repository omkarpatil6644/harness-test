# LLM Accuracy Frameworks
Frameworks for testing LLM accuracy.

This repository provides scripts and utilities to automate the evaluation of large language models (LLMs) using **lm-evaluation-harness**.  
It supports evaluating both **base** and **instruct** models and aggregating results across multiple benchmarks.

---

## Prerequisites

Before starting, ensure the following are installed:

- Python >=3.10
- Git
- CUDA-compatible GPU (recommended for large models)
- `pip`
- OS - Linux
- Bash shell

---

## Installation

### Step 1: Create Virtual Environment (Highly Recommended)

### Step 2: Download Setup Script(Clone this repository)
```bash
git clone https://github.com/AGL-Innominds-Libraries-and-Tools/llm-accuracy-frameworks.git
cd your-repo-directory
```

### Step 3: Make Script Executable
```bash
chmod +x setup/lm_eval_harness_setup.sh
```

### Step 4: Run Setup Script (One-Time Process)
```bash
setup/lm_eval_harness_setup.sh
```

### Usage
Running Evaluations

### Basic evaluation command structure:
Uncomment the models you wish to evaluate in models.yaml before running the command.

### Option 1: Below command uses default models.yaml
```bash
python evaluate/run_eval.py <leaderboard_task> <path_to_store_results>
```

### Option 2: Custom path to models.yaml.
```bash
python evaluate/run_eval.py <leaderboard_task> <path_to_store_results> --config <custom_models.yaml_path>
```

Note: Some HuggingFace models require executing custom repository code.
If you encounter this error: Please pass the argument `trust_remote_code` to allow custom code to be run. Please use the below command with additional argument --trust-remote-code
```bash
python evaluate/run_eval.py <leaderboard_task> <path_to_store_results> --trust-remote-code
```



### Available Tasks
- leaderboard_bbh
- leaderboard_gpqa
- leaderboard_ifeval
- leaderboard_math_hard
- leaderboard_mmlu_pro
- leaderboard_musr
- leaderboard (Runs all available tasks. Note: Not recommended for single runs as it is time-consuming.)

### Results Directory Structure
```text
results/
├── model_name/
│   ├── raw_results/
│   │   ├── *.json
│   ├── normalized_results/
│   │   ├── *.json
|__ aggregated_results.csv