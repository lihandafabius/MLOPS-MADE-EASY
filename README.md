# MLOPS Made Easy: From Infrastructure to Fully Automated ML Deployments

A hands-on, end-to-end guide to the machine learning lifecycle. Each module explains the concepts, then builds a working project you can run, break and extend.

By the end you will have taken a model from a notebook experiment to a tracked, orchestrated, deployed and monitored production service, with the infrastructure and CI/CD around it defined as code.

## The lifecycle

```
 Data ─► Experiment ─► Pipeline ─► Registry ─► Deploy ─► Monitor
  │          │            │           │          │          │
  └──────────┴────────────┴───────────┴──────────┴──────────┘
                    feedback: retrain, rollback, improve
```

## Modules

| # | Module | What you build | Key tools |
|---|--------|----------------|-----------|
| 00 | [Introduction to MLOps](00-introduction/) | The mental model: what MLOps is, why it exists, how it fits with other fields | n/a |
| 01 | [Experiment Tracking & Model Management](01-experiment-tracking/) | Tracked experiments, hyperparameter search, a model registry | MLflow |
| 02 | [Orchestration & ML Pipelines](02-orchestration/) | A reproducible training pipeline run by more than one orchestrator | Prefect, Mage, Airflow, Dagster |
| 03 | [Model Deployment](03-deployment/) | The same model served as batch, online and streaming | Flask, Docker, MLflow Registry, Kinesis, Lambda, Mage |
| 04 | [Model Monitoring](04-monitoring/) | Metrics, drift and data quality checks feeding live dashboards | Evidently, PostgreSQL, Grafana, Docker Compose |
| 05 | [Capstone: Infra to Automated Deployment](05-capstone/) | Everything above on cloud infrastructure with CI/CD and retraining | Terraform, Kubernetes, GitHub Actions |

## Running the projects

Each module is self-contained and has its own `README.md`, `requirements.txt` and, where needed, a `docker-compose.yml`.

Prerequisites:
- Python 3.10+
- Docker and Docker Compose
- Git
- An AWS account (only for the streaming and capstone parts)

```bash
git clone https://github.com/<your-username>/MLOPS-MADE-EASY.git
cd MLOPS-MADE-EASY
python -m venv .venv && source .venv/bin/activate
```

Then follow the README inside the module you want.

## Repository layout

```
mlops-handbook/
├── 00-introduction/
├── 01-experiment-tracking/
├── 02-orchestration/
├── 03-deployment/
├── 04-monitoring/
├── 05-capstone/
├── data/              # small sample datasets, large ones are downloaded by scripts
└── docs/              # diagrams and extra notes
```

## Running example

The modules share one running problem, predicting taxi trip duration. It is small enough to run on a laptop, yet realistic enough to expose real MLOps problems: changing data, retraining, serving latency and drift.

## Acknowledgements

The module outline is inspired by the open-source [MLOps Zoomcamp](https://github.com/DataTalksClub/mlops-zoomcamp) from DataTalks.Club. All explanations and code here are written independently. Go and take the course too.

## Contributing

Issues and pull requests are welcome. Please keep each module runnable end to end.

## License

MIT
