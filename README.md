# Secure Computing Project: Code Analysis with Language Models

## Overview

This repository contains the **SecureProject.ipynb** Jupyter Notebook, which demonstrates the use of state-of-the-art language models for security code analysis. The notebook provides interactive examples for both vulnerability detection and functional validation of Java code snippets using various prompts and multiple language models.

## Features

- **Multi-Model Integration:** Leverages several LLMs, including CodeLlama, Llama2 Chat, StarCoder2, WizardCoder-Python, and Mistral-7B-Instruct.
- **Vulnerability Analysis:** Uses zero-shot and chain-of-thought prompts to identify potential security vulnerabilities in Java code.
- **Functional Validation:** Evaluates whether Java methods correctly implement intended functionalities such as secure password storage and email validation.
- **Combined Prompt Analysis:** Uses zero-shot and chain-of-thought prompts to identify potential security vulnerabilities and functional vulnerabilities in a Java code.
- **Interactive Demonstrations:** Generates and prints responses directly within the notebook, showcasing how different models approach code analysis.
- **Resource Management:** Includes cleanup procedures to free GPU memory and delete cache directories after execution.

## Notebook Description

The **SecureProject.ipynb** notebook is structured into several sections:

- **Installation Commands:** Installs required libraries such as `transformers`, `accelerate`, `bitsandbytes`, `auto-gptq`, `peft`, and `triton` to support model quantisation and execution.
- **Prompt Definitions:** Contains example Java code snippets and corresponding prompts for vulnerability detection and functional validation. Prompts are defined in both zero-shot and chain-of-thought formats.
- **Model Initialisation and Response Generation:**  
  - **CodeLlama Pipeline:** Initialises the CodeLlama model with 4-bit quantisation and generates responses for the defined prompts.  
  - **Llama2 Chat Pipeline:** Formats the input as a conversation and generates responses using the Llama2 Chat model.
  - **StarCoder2 Pipeline:** Uses StarCoder2 to generate deterministic and varied outputs for code analysis.
  - **WizardCoder-Python Pipeline:** Implements response generation with detailed configuration for 4-bit quantisation.
  - **Mistral-7B-Instruct Pipeline:** Formats prompts as required by Mistral and generates responses accordingly.
- **Execution and Output:** Each section prints the outputs for vulnerability detection and functional validation using both zero-shot and chain-of-thought approaches.
- **Cleanup Procedures:** Contains functions to clear GPU memory and delete local cache directories, ensuring efficient resource management after model execution.

## Implementation Details

### Vulnerability Detection

The notebook includes Java code snippets that exemplify common security vulnerabilities, such as:
- SQL Injection and insecure handling of user inputs.
- Server-Side Request Forgery (SSRF) vulnerabilities.
- Denial-of-Service (DoS) via uncontrolled thread creation.

For each snippet, prompts are defined in two formats:
- **Zero-shot:** A brief analysis request.
- **Chain-of-Thought:** A detailed, step-by-step reasoning prompt.

### Functional Validation

Java methods intended to securely handle passwords and validate emails are also analysed. The notebook verifies whether these implementations meet their intended security goals by:
- Generating zero-shot responses to quickly assess code functionality.
- Generating chain-of-thought responses for a deeper, step-by-step analysis.

### Combined Prompt Analysis

Java scripts containing both code vulnerabilities and functional vulnerabilities. Such vulnerabilities include:
- SQL Injection Vulnerability
- File Path Traversal Vulnerability
- DoS Vulnerability

For each snippet, prompts are defined in two formats:
- **Zero-shot:** A brief analysis request.
- **Chain-of-Thought:** A detailed, step-by-step reasoning prompt.

### Multi-Model Comparison

The notebook demonstrates how different models handle the same prompts:
- **CodeLlama:** Focuses on concise, instructive responses.
- **Llama2 Chat:** Emulates conversational analysis with a simulated dialogue format.
- **StarCoder2:** Produces both deterministic and varied responses based on configuration.
- **WizardCoder-Python:** Applies robust quantisation techniques for enhanced performance.
- **Mistral-7B-Instruct:** Formats prompts for clear, instructive output.

## Repository Structure

The repository structure is as follows:

```
project-root/
├── README.md                 # Project documentation (this file)
├── Benchmarks.xlsx           # Spreadsheet with benchmark results
└── SecureProject.ipynb       # Main source code directory
```

### Resource Management

At the end of the notebook, cleanup functions are executed to:
- Remove downloaded caches.
- Clear GPU memory via garbage collection and CUDA cache clearance.
- Ensure that all models and tokenisers are deleted from memory to prevent resource leaks.

## Usage

To run the notebook and see the live demonstrations:

1. Open the Jupyter Notebook:
   ```bash
   jupyter notebook SecureProject.ipynb
   ```
2. Execute the notebook cells sequentially to observe the installation steps, model initialisations, prompt responses, and cleanup procedures.

## Results

When you run the notebook, you will observe:
- **Printed Responses:** Detailed outputs from each language model for both vulnerability detection and functional validation tasks.
- **Efficient Resource Cleanup:** Confirmation messages indicating that caches and GPU memory have been cleared after execution.
