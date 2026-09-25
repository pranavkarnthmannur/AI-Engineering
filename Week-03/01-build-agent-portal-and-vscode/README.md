# Microsoft Foundry IT Support Agent

## Overview

This project builds an IT Support Agent using Microsoft Foundry and Python.

The agent can answer IT policy questions and analyse system performance data using tools configured in Microsoft Foundry.

## Tools Used

- Microsoft Foundry
- Python
- Azure AI Projects SDK
- File Search
- Code Interpreter
- Azure CLI
- VS Code

## Agent Capabilities

### File Search
The agent uses an IT policy document as a knowledge source to answer questions such as password reset policies.

### Code Interpreter
The agent analyses system performance CSV data and can identify CPU and memory usage patterns and generate charts.

## Python Integration

A Python client connects to the Microsoft Foundry project, loads the configured agent, creates a conversation, and allows the user to interact with the agent from the terminal.

## What I Learned

- Creating and configuring an AI agent in Microsoft Foundry
- Adding File Search and Code Interpreter tools
- Connecting Python to a Foundry agent
- Using environment variables for configuration
- Testing tool selection through natural-language prompts
- Working with agent conversations through the Azure AI Projects SDK

## Security

Project configuration is stored in a `.env` file, which is excluded from Git using `.gitignore`.