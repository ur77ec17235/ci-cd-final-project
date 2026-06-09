# CI/CD Tools and Practices Final Project Template

## Project name
ci-cd-final-project

## Overview
This project is the final assignment for the **Continuous Integration and Continuous Delivery (CI/CD)** course.  
The goal of this project is to build a complete CI/CD workflow for a Python microservice that provides a RESTful API for managing counters.

The project demonstrates how to:
- automate code quality checks with **GitHub Actions**
- automate testing with **nose**
- create **Tekton tasks** for CI/CD in OpenShift
- create an **OpenShift Pipeline** for linting, testing, building, and deploying the application
- deploy the application to an OpenShift cluster

---

## Objectives completed
The following objectives were implemented in this project:

### 1. Continuous Integration with GitHub Actions
A GitHub Actions workflow was created to automatically run when:
- code is pushed to the `main` branch
- a pull request is opened against the `main` branch

The workflow includes these steps:
- **Checkout**
- **Install dependencies**
- **Lint with flake8**
- **Run unit tests with nose**

### 2. Continuous Delivery with OpenShift Pipelines
Tekton tasks were created and applied to the OpenShift cluster:
- **cleanup**
- **nose**

An OpenShift pipeline was created with the following stages:
- cleanup
- git clone
- flake8 linting
- nose unit tests
- build image with buildah
- deploy application to OpenShift

### 3. Deployment
The application is deployed automatically through the OpenShift pipeline using the OpenShift client task and the deployment command.

---

## Project structure
Important files used in this project:

```text
.
├── .github/
│   └── workflows/
│       └── workflow.yml
├── .tekton/
│   └── tasks.yml
├── app/
├── tests/
├── requirements.txt
└── README.md