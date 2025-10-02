README
Overview
This dataset was created to support experiments on blockchain attack detection. Raw logs from simulated blockchain environments were parsed into structured CSV datasets using the pipeline_unified.py pipeline.
Files Included
      •	blockchain_logs2.txt:  Raw log for Dataset A.
      •	blockchain_logs3.txt:  Raw log for Dataset B.
      •	Dataset_A.csv:  Processed structured Dataset A.
      •	Dataset_B.csv:  Processed structured Dataset B.
      •	otheranalysis.py:  Python pipeline for parsing, feature extraction, ML, and evaluation.
      •	Jupyter notebooks (InitialMLanalysis.ipynb, Raw Simulation.ipynb):  Supplementary exploratory analyses.
How to Reproduce
Ensure Python =3.10 with required libraries:
      •	pip install numpy pandas scikit-learn imbalanced-learn matplotlib
      •	python .\pipeline_unified.py --dataA .\blockchain_logs2.txt --dataB .\blockchain_logs3.txt --outdir .\results --sampler smote
Outputs generated in .\results\:
      •	Structured datasets (CSV)
      •	Cross-validation metrics
      •	Per-attack evaluation
      •	Summary tables and plots
Data Processing Notes
      •	SMOTE was used to balance classes where specified.
      •	Each log line is parsed into an event row with engineered features.
      •	Binary attack labels assigned for supervised ML tasks.
Usage
These datasets can be used for:
      •	Blockchain security research.
      •	Machine learning attack detection experiments.
      •	Reproducibility of published results.


METADATA
Software/Code Used:
      •	Python 3.10+
      •	pipeline_unified.py (custom parsing and ML pipeline script)
      •	Libraries: numpy, pandas, scikit-learn, imbalanced-learn, matplotlib

Data Sources:
      •	blockchain_logs2.txt Parsed into Dataset A
      •	blockchain_logs3.txt Parsed into Dataset B

File Descriptions:
      •	blockchain_logs2.txt: Raw simulation log capturing multiple blockchain security attack scenarios (hash-rate manipulation, smart contract audit, denial-of-chain).
      •	blockchain_logs3.txt: Extended raw simulation log with additional attacks (Sybil, Eclipse, Finney, Timejacking).
      •	Dataset_A.csv: Structured dataset extracted from blockchain_logs2.txt with feature vectors.
      •	Dataset_B.csv: Structured dataset extracted from blockchain_logs3.txt with richer event coverage.
      •	OtherAnalysis.py: End-to-end pipeline for log parsing, feature extraction, ML experiments, and evaluation.
      •	InitialMLanalysis.ipynb / Raw Simulation.ipynb: Jupyter notebooks for exploratory analysis and reproducing raw simulations.

Variables:
      • event: Type of blockchain event (e.g., add_node, tx_added, sybil_nodes).
      • hash_rate: Reported hash rate of a node.
      • blocks_before / blocks_after: Chain length before and after event.
      •	blocks_delta: Difference between before/after blocks.
      •	tx_added: Indicator if transaction was successfully added (1) or rejected (0).
      •	doc_flag: Flag for Denial of Chain attack.
      •	nodes_count: Number of nodes recorded (esp. Sybil/Eclipse).
      •	attack_type: Attack classification (Hashrate, SmartContract, DoC, Sybil, Eclipse, Finney).
      •	label_attack: Binary label (1 = malicious/attack, 0 = benign).

Units of Measurement: All values are counts, hash rates (arbitrary simulation units), or binary flags.

Confidentiality: All data are synthetic, simulated in a controlled environment. No personal or sensitive data.


