# DevOps Capstone Project / CI-CD Final Project

[![CI Workflow](https://github.com/suhanib-18/cd0215en-cicd-final-project/actions/workflows/workflow.yml/badge.svg)](https://github.com/suhanib-18/cd0215en-cicd-final-project/actions)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Python 3.9](https://img.shields.io/badge/Python-3.9-green.svg)](https://shields.io/)

This repository contains the complete implementation for the **IBM Continuous Integration and Continuous Delivery (CI/CD) Final Project** (DevOps Capstone). It showcases a Customer Accounts Microservice with **RESTful APIs**, automated testing with **Nose**, linting with **Flake8**, Continuous Integration via **GitHub Actions**, and Continuous Delivery on **Red Hat OpenShift** using **Tekton Pipelines**.

---

## Project Overview

- **Project Name:** DevOps Capstone Project – CI/CD Final Project
- **Author:** suhanib-18
- **Microservice:** Customer Accounts Service
- **Technologies Used:** Python 3.9, Flask, Flake8, Nose, Tekton Pipelines, Red Hat OpenShift, Kubernetes, Docker

The microservice provides a RESTful API for managing customer accounts:
- `GET /health` - Service health status
- `GET /accounts` - List all customer accounts
- `POST /accounts` - Create a new customer account
- `GET /accounts/{id}` - Retrieve account details
- `PUT /accounts/{id}` - Update account details
- `DELETE /accounts/{id}` - Delete an account by id

---

## CI/CD Pipeline Architecture

### 1. Continuous Integration with GitHub Actions
- **Trigger:** Automated trigger on `push` and `pull_request` events to `main`
- **Workflow:** `.github/workflows/workflow.yml`
- **Quality Gates:**
  - Automated dependency setup with Python 3.9
  - Strict code linting using `flake8`
  - Automated unit testing with `nosetests`

### 2. Continuous Delivery with Tekton on Red Hat OpenShift
- **Tasks:** `.tekton/tasks.yml` (`cleanup`, `nose`)
- **Pipeline:** `.tekton/pipeline.yml`
- **Workspace:** OpenShift PersistentVolumeClaim (`pvc.yaml`)

---

## Repository Structure

```
.github/workflows/workflow.yml   # GitHub Actions CI (flake8 + nose)
.tekton/tasks.yml                # Tekton cleanup + nose tasks
.tekton/pipeline.yml             # OpenShift Tekton pipeline
service/                         # Flask microservice
tests/                           # Unit tests
```
