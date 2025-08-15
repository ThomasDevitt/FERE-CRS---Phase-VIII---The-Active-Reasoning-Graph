
# FERE-CRS Phase VIII: The Active Reasoning Graph (Supplementary Materials)

This repository contains the complete source code, configuration files, and experimental data required to reproduce the results presented in the manuscript, "FERE-CRS Phase VIII: The Active Reasoning Graph — A Vindicative Methodology for the Calculus of Cognitive Autonomy."

## Synopsis

This project implements and validates the Active Reasoning Graph (ARG), a novel neuro-symbolic architecture designed to overcome the brittleness of Large Language Models (LLMs) in complex reasoning tasks. The ARG-Agent uses a formal, inspectable graph structure as its mental workspace and leverages a constrained LLM as a "Graph Operator." Its reasoning is guided by a proactive, skeptical Meta-Reasoning Agent (MRA) whose policies are derived from the principles of Active Inference and the Calculus of Cognitive Autonomy.

This script runs a controlled experiment comparing the ARG-Agent against a strong baseline LLM on a deceptive reasoning task, demonstrating the ARG architecture's superior robustness and ability to avoid common LLM failure modes like "Creative Avoidance."

## Directory Structure

The project is organized as follows to ensure a clean separation between code, configuration, and data.

/FERE-CRS_PhaseVIII/
|
|-- run_feres_experiment8.py # The main executable Python script for the experiment.
|-- requirements.txt # A list of all required Python libraries.
|-- .env.example # A template for the environment variables file.
|-- README.md # This documentation file.
|
|-- /inputs/ # Contains all necessary input files for the script.
| |-- /config/
| | |-- config.ini # Main configuration for the experiment (run modes, models, etc.).
| |
| |-- /test_suites/
| | |-- conceptual_brittleness_test_suite.json # The experimental problems.
|
|-- /results/ # Directory where all outputs (logs, data, plots) will be saved.
# This directory is created automatically by the script.

## System Requirements

* Python 3.10 or higher
* `pip` (Python package installer)
* An active Google AI API key with access to the Gemini family of models.

## Setup & Installation

Please follow these steps to set up the environment and run the experiment.

**1. Clone the Repository**
```bash
git clone <repository_url>
cd FERE-CRS_PhaseVIII
2. Create a Python Virtual Environment (Recommended)
Using a virtual environment is a best practice to avoid conflicts with other projects.
Bash
# For Windows
python -m venv venv
.\venv\Scripts\activate

# For macOS/Linux
python3 -m venv venv
source venv/bin/activate
3. Install Dependencies
Install all required Python libraries from the requirements.txt file.
Bash
pip install -r requirements.txt
4. Configure Your API Key
The script securely loads your API key from a .env file.
1.	Make a copy of the template file: cp .env.example .env (on macOS/Linux) or copy .env.example .env (on Windows).
2.	Open the newly created .env file with a text editor.
3.	Replace the placeholder text with your actual Google AI API key.
4.	# .env file content
5.	GOOGLE_API_KEY="AIzaSy...your...secret...key..."
Note: This file is intentionally excluded from version control to protect your credentials. Never share your .env file.
Running the Experiment
The main script is controlled by the settings in inputs/config/config.ini.
Configuration:
Before running, you can edit config.ini to change the experiment parameters:
•	run_mode: Set to FULL_SUITE (default) to run both the ARG-Agent and the Baseline. Set to CW-LM or B-LM to run only one agent.
•	log_level: Set to DEBUG to see highly detailed output, including the MRA's internal decision metrics. Set to INFO for standard output.
•	output_directory: Change this to create a new folder for your results.
Execution:
To run the full experiment, execute the main script from the root directory of the project:
Bash
python run_feres_experiment8.py
Expected Output
After a successful run, the output_directory specified in your config.ini (e.g., results/run_001_graph/) will contain the following files:
1.	experiment_run_[timestamp].log: A detailed log file of the entire experimental process, including MRA decisions and LLM interactions.
2.	experiment_results.csv: A CSV file containing the structured results for each trial, including agent type, success score, and failure mode classification.
3.	1_success_rate_final.png: A bar chart showing the overall success rate of the ARG-Agent vs. the Baseline-LM.
4.	2_failure_modes_final.png: A stacked bar chart visualizing the proportion of failure modes (e.g., Confabulation, Robust Failure) for each agent.
5.	3_performance_by_category_final.png: A grouped bar chart comparing the agents' performance on each problem category in the test suite.

Citing this Work
If you use this code or the concepts from the FERE-CRS project in your research, please cite our manuscript:
Code snippet
@article{Devitt2025FERECRS_PhaseVIII,
  title   = {{FERE-CRS Phase VIII: The Active Reasoning Graph — A Vindicative Methodology for the Calculus of Cognitive Autonomy}},
  author  = {Devitt, Thomas E.},
  journal = {arXiv preprint},
  year    = {2025},
  note    = {Research conducted in collaboration with Google's Gemini model.}
}
License
This project is licensed under the MIT License. See the LICENSE file for details. This means you are free to use, modify, and distribute the code for any purpose, including commercial use, as long as you include the original copyright and license notice.

