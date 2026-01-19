# Runbook

## Prerequisites
- Python 3.10+
- Azure/Fabric workspace (later)
- Git

## Local steps
1. Create virtual env
2. Run data generator → outputs to data/sample or data/raw
3. Validate basic checks

## Cloud steps (Fabric)
1. Create workspace + lakehouse
2. Upload Bronze files
3. Run notebook transforms to Silver/Gold
4. Connect Power BI to SQL endpoint
