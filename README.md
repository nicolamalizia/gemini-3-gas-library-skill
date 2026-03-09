# Gemini 3 GAS Library Skill

A specialized skill for Gemini CLI to assist with Google Apps Script (GAS) library development, management, and integration.

## Overview

This skill provides expert guidance and automated workflows for:
- Creating and maintaining Google Apps Script libraries.
- Managing library versions and deployments via `clasp`.
- Documenting library functions for optimal IDE autocompletion.
- Handling cross-project dependencies and permissions.

## Features

- **Standardized Scaffolding:** Quickly set up new GAS library projects with best practices.
- **Version Management:** Streamlined workflows for tagging and deploying new versions.
- **Auto-Documentation:** Tools to ensure your library functions are properly documented with JSDoc for use in other projects.
- **Integration Support:** Assistance in connecting libraries to consumer scripts.

## Installation

To install this skill in your Gemini CLI environment:

1. Clone this repository or copy the `SKILL.md` file.
2. Link the skill to your Gemini configuration (refer to Gemini CLI documentation for specific `skill link` commands).

## Usage

Once activated, you can invoke this skill by asking Gemini questions related to GAS libraries, such as:
- "How do I structure a new GAS library?"
- "Help me deploy a new version of this library."
- "Generate JSDoc for my library functions."

## Requirements

- [clasp](https://github.com/google/clasp) (Command Line Apps Script Projects)
- Node.js & npm (for clasp and development tools)
