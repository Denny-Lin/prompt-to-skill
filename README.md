# prompt-to-skill

Turn vague prompts into structured, reusable AI skills.

---

## Overview

Most users do not know exactly what they want at the beginning.

They start with vague prompts such as:
- "help me improve this"
- "make this better"
- "summarize this"

However, what they actually need is a clear and reusable specification.

This project bridges that gap by transforming unclear intent into structured, reusable skills.

---

## What This Does

prompt-to-skill helps you:

- Explore outputs generated from vague prompts
- Identify what a "good result" looks like
- Extract patterns from selected outputs
- Convert those patterns into reusable skill definitions

---

## Core Workflow

Vague Prompt  
→ Generate Multiple Outputs  
→ Select Preferred Output  
→ Extract Structure and Patterns  
→ Generate Skill Specification  
→ Reusable Skill  

---

## Example

### Input (Vague Prompt)

```
help me summarize this
```

### Output (AI Generated)

```
- Key point A
- Key point B
- Key point C
```

### Generated Skill

```yaml
name: summarize_text
purpose: Summarize text into key bullet points

input:
  text: string

output:
  bullets: array[string]

constraints:
  - 3 bullet points
  - each under 20 words
  - no new information
```

---

## Why This Matters

Writing good prompts is difficult.

However, recognizing a good result is much easier.

Instead of requiring users to define requirements upfront, this project allows them to:

discover → select → refine → formalize

---

## Project Goals

- Make prompt engineering more intuitive
- Enable reusable AI capabilities (skills)
- Reduce trial-and-error in prompt writing
- Bridge natural language and structured specifications

---

## MVP Features

- Input a vague prompt
- Generate multiple candidate outputs
- Allow user selection of preferred result
- Automatically generate a structured skill definition

---

## Future Work

- Skill library and sharing system
- Versioning and comparison of skills
- Prompt-to-API generation
- Integration with agents and tool calling
- Evaluation and scoring mechanisms
- Learning from user-selected outputs

---

## Tech Stack

To be determined.

Possible options:
- Frontend: React / Next.js
- Backend: Python / Node.js
- LLM: OpenAI or compatible providers

---

## Philosophy

Do not start with perfect instructions.

Start with imperfect intent, then refine into clarity.

---

## Contributing

Contributions, ideas, and feedback are welcome.
