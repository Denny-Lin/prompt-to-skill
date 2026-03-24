# prompt-to-skill

Turn vague prompts into structured, reusable AI skills.

## Overview

Most users do not know exactly what they want at the beginning.

They start with vague prompts such as:

- "help me improve this"
- "make this better"
- "summarize this"

What they actually need is not just a better answer, but a clear, reusable specification.

`prompt-to-skill` is a project for transforming unclear intent into structured AI skills that can be reused, versioned, and extended.

## Problem

Current AI tools are good at generating responses, but they are not always good at turning good responses into reusable systems.

Common pain points:

- Users do not know how to express requirements clearly
- Good outputs are not converted into repeatable patterns
- Prompts are hard to standardize across models and platforms
- There is no easy way to turn an ad hoc interaction into a persistent skill

## Solution

This project provides a workflow for:

1. Starting from a vague prompt
2. Generating multiple candidate outputs
3. Letting the user choose the best result
4. Extracting patterns from that result
5. Converting the pattern into a reusable skill definition

The goal is to bridge natural language and structured AI behavior.

## Core Workflow

```text
Vague Prompt
    ↓
Generate Multiple Outputs
    ↓
Select Preferred Output
    ↓
Extract Structure and Patterns
    ↓
Generate Skill Specification
    ↓
Reusable Skill
```

## What This Project Produces

A skill is represented as a structured file that can include:

- name
- purpose
- trigger
- inputs
- outputs
- constraints
- instructions
- examples
- metadata

This makes the skill readable by humans and usable by software.

## Example

### Input

```text
help me summarize this
```

### Candidate Output

```text
- Key point A
- Key point B
- Key point C
```

### Generated Skill

```yaml
name: summarize_text
purpose: Summarize text into key bullet points

trigger:
  - summarize
  - summarize this
  - summarize the text

inputs:
  text:
    type: string
    required: true
  max_points:
    type: integer
    required: false
    default: 3

outputs:
  bullets:
    type: array
    items: string

constraints:
  - no new information
  - concise output
  - 3 to 5 bullet points

instructions: |
  Summarize the input text into concise bullet points.
  Do not add information that is not present in the input.

examples:
  - input:
      text: "..."
    output:
      bullets:
        - "..."
```

## Why This Matters

Writing a good prompt is hard.

Recognizing a good result is much easier.

This project lets users move from:

- guessing
- to selecting
- to refining
- to formalizing

The result is a reusable skill instead of a one-time answer.

## Project Goals

- Make prompt engineering more intuitive
- Convert vague intent into structured skill definitions
- Support reusable AI capabilities
- Reduce prompt trial and error
- Provide a standard format that can be extended across platforms

## Design Principles

### 1. Human-readable

The skill format should be easy to read and edit.

### 2. Machine-friendly

The same skill should be easy to parse, validate, and transform.

### 3. Model-agnostic

The core format should not depend on one specific model or vendor.

### 4. Extensible

New fields, adapters, and output targets should be easy to add later.

## Proposed Skill Format

A skill definition may be stored as YAML or JSON.

Recommended source format:

- YAML for editing and version control
- JSON for runtime use or API integration

Example structure:

```yaml
name: string
purpose: string
trigger: list[string]
inputs: object
outputs: object
constraints: list[string]
instructions: string
examples: list[object]
metadata: object
```

## Future Extensions

This project can grow into a broader platform with:

- Skill library
- Version history
- Comparison tools
- Prompt-to-spec generation
- Export to OpenAI, LangChain, or other agent frameworks
- Validation and evaluation tools
- Human-in-the-loop refinement
- Skill sharing and reuse

## MVP Scope

The first version can be very small:

- Input a vague prompt
- Generate a few candidate outputs
- Let the user choose one
- Convert the selected result into a structured skill file
- Save the skill for reuse

## Suggested Folder Structure

```text
prompt-to-skill/
├── skills/
│   └── summarize_text.yaml
├── src/
├── README.md
└── LICENSE
```

## Tech Stack

This project is implementation-agnostic.

Possible choices:

- Frontend: React, Next.js
- Backend: Python, Node.js
- LLM provider: OpenAI or compatible APIs
- Storage: Local files, database, or object storage

## Contributing

Ideas, feedback, and contributions are welcome.
