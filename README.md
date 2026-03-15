# MLOPS-Complete-ML-Pipeline
his project covers the end to end understanding for creating an ML pipeline and working around it using DVC for experiment tracking and data versioning(using AWS S3)

## ML PipeLine Architecture

Data Ingestion -> Pre Processing -> Feature Engg -> Model Training -> Model Evaluation 



# Logging Concept in Python (MLOps)

## Overview
Logging is the process of recording events, messages, warnings, and errors that occur while a program is running.  
It helps developers monitor applications, debug issues, and understand program behavior during execution.

In machine learning and MLOps pipelines, logging is widely used to track data processing, model training, pipeline execution, and errors.

---

## Why Logging is Important

Logging is important because it helps in:

- Debugging errors in applications
- Monitoring program execution
- Tracking machine learning pipelines
- Recording system events
- Maintaining a history of application behavior

Unlike `print()` statements, logging provides structured and configurable messages.

---

## Logging Levels

Python provides different logging levels to categorize messages.

| Level | Description |
|------|-------------|
| DEBUG | Detailed information used for debugging |
| INFO | General information about program execution |
| WARNING | Indicates something unexpected happened |
| ERROR | A serious issue occurred |
| CRITICAL | Very severe error that may stop the program |

---

## Basic Logging Example

``` import logging
import yaml


# Ensure the "logs" directory exists
log_dir = 'logs'
os.makedirs(log_dir, exist_ok=True)


# logging configuration
logger = logging.getLogger('data_ingestion')
logger.setLevel('DEBUG')

console_handler = logging.StreamHandler()
console_handler.setLevel('DEBUG')

log_file_path = os.path.join(log_dir, 'data_ingestion.log')
file_handler = logging.FileHandler(log_file_path)
file_handler.setLevel('DEBUG')

formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')
console_handler.setFormatter(formatter)
file_handler.setFormatter(formatter)

logger.addHandler(console_handler)
logger.addHandler(file_handler) ```