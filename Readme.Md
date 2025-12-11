# Jenkins Declarative Pipeline Demo

This repository contains a sample **Jenkins Declarative Pipeline** (`Jenkinsfile`) used for practicing CI/CD concepts.  
The pipeline demonstrates parameters, environment variables, build stages, and post‑build actions.

---

## 🚀 Pipeline Overview

- **Agent**: Runs on a Jenkins node labeled `Agent-1`.
- **Environment Variables**:  
  - `GREETING = "Hello Jenkins"`
- **Options**:  
  - Timeout after 2 minutes  
  - Prevent concurrent builds
- **Parameters**:  
  - `PERSON` – string input (default: *Mr Jenkins*)  
  - `BIOGRAPHY` – text input for free‑form info  
  - `TOGGLE` – boolean flag (default: true)  
  - `CHOICE` – dropdown with values (*One, Two, Three*)  
  - `PASSWORD` – masked password input (default: *SECRET*)

---

## 🛠️ Stages

1. **Build**  
   Prints a simple build message.

2. **Test**  
   Prints a test message.

3. **Checking Params**  
   Echoes all pipeline parameters to the console:
   - Person name  
   - Biography text  
   - Toggle value  
   - Choice selection  
   - Password (masked in Jenkins UI)

4. **Deploy**  
   Runs a shell script that:
   - Prints deployment messages  
   - Echoes the `GREETING` environment variable  
   - Sleeps for 10 seconds  
   - Prints webhook configuration message

---

## 📦 Post Actions

- **always** → Prints *I am Forever*  
- **failure** → Prints *this runs when pipeline is failed :( *  
- **success** → Prints *This build is successful :) *

---

## ▶️ How to Use

1. Copy the pipeline code into a file named `Jenkinsfile`.
2. Push it to your GitHub repository.
3. In Jenkins:
   - Create a new pipeline job.
   - Point it to this repository.
   - Run the job to see the stages execute.

---

## 🎯 Purpose

This pipeline is for **practice and learning**:
- Understanding Jenkins declarative syntax
- Exploring parameters and environment variables
- Observing build/test/deploy flow
- Experimenting with post‑build actions

---

Happy practicing with Jenkins pipelines ✨
