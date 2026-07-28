# AI Prompt Library for Orthodontic Patient Consultation Follow-Up

**Case Study:** Barbosa Orthodontics  
**Course:** MAI 600 – Module 4  
**Student:** Juliana do Espirito Santo

## Project Overview

This project develops and evaluates a reusable prompt library for a healthcare-administration workflow. The selected task is to summarize fictional orthodontic consultation notes and recommend safe administrative follow-up actions.

The project is inspired by common workflows at Barbosa Orthodontics. However, all scenarios are fictional and contain no protected health information, real patient information, or confidential business data.

## Problem Description

Orthodontic consultations may contain information about treatment interests, financial concerns, insurance questions, and scheduling preferences. When notes are written in different styles, important details may be overlooked during follow-up.

A structured AI prompt can help administrative staff organize the information consistently. The goal is not to replace clinical judgment. The goal is to support the treatment coordinator and front desk by producing clear, grounded, and professional summaries.

## Task Selected

Summarize fictional orthodontic consultation notes and recommend the next administrative action.

## Intended Users

- Treatment coordinator
- Front desk team
- Office manager
- Marketing and patient follow-up staff

## Why the Task Matters

Consistent summaries can help the office:

- Reduce time spent reviewing free-form notes
- Identify patient concerns more quickly
- Improve follow-up consistency
- Avoid missing insurance, financial, or scheduling details
- Support a more personalized patient experience

## What a Good Response Should Include

A strong response should include:

1. Patient concern or goal
2. Treatment interest
3. Financial or insurance questions
4. Scheduling preferences
5. Recommended administrative next action
6. Missing information

The response must remain grounded in the notes and avoid medical advice, invented treatment recommendations, unsupported insurance decisions, or fabricated financing information.

## Dataset

The evaluation set contains 10 fictional orthodontic consultation cases. Each case is safe for public GitHub publication.

## Prompting Approach

The prompt library contains five prompt types:

- P1: Zero-shot prompt
- P2: Structured prompt
- P3: Few-shot prompt
- P4: Safety and uncertainty prompt
- P5: Final improved prompt

The prompts were designed to improve role clarity, output consistency, grounding, uncertainty handling, and professional tone.

## Evaluation Criteria

Each tested response is scored from 1 to 5 using:

- Accuracy
- Helpfulness
- Format adherence
- Completeness
- Evidence and grounding
- Safety and professionalism
- Clarity

## Results Summary

The early prompts were useful but inconsistent. Common problems included missing information, format drift, and unsupported assumptions. Prompt 5 performed best because it combined a clear role, required fields, evidence-only instructions, uncertainty rules, and a professional tone.

## Failure Modes Found

### Incomplete Answer
Some early responses missed financial concerns or scheduling preferences.

**Mitigation:** Require exact output fields.

### Unsupported Assumptions
Some responses assumed insurance coverage or financing approval.

**Mitigation:** Add an evidence-only rule and require “Not provided” when information is missing.

### Format Drift
Some responses used paragraphs instead of the requested structure.

**Mitigation:** Provide an exact markdown table schema.

### Tone Mismatch
Some responses sounded too casual for a healthcare administration workflow.

**Mitigation:** Define the audience and require a concise, professional tone.

## Final Best Prompt

Prompt 5 was the best-performing prompt because it included:

- A specific administrative role
- A clear audience
- Required table columns
- A rule to use only the provided notes
- A rule to avoid medical advice
- A rule not to invent insurance, financing, treatment, or scheduling information
- A missing-information instruction

See `prompt_library.md` for the complete prompt.

## Limitations

This project uses fictional cases and does not represent a production clinical system. Human review remains necessary. The model should not make clinical decisions, interpret treatment plans, promise insurance coverage, or communicate directly with patients without staff review.

## Repository Structure

```text
mai600-module4-barbosa-orthodontics/
│
├── README.md
├── prompt_library.md
├── evaluation_set.csv
├── results_table.csv
├── before_after_prompt_improvements.csv
├── failure_mode_analysis.csv
├── prompt_revision_rescore.csv
├── ai_usage_disclosure.md
│
├── examples/
│   └── sample_outputs.md
│
├── notebooks/
│   └── prompt_evaluation_template.ipynb
│
└── images/
```

## Reflection

This project helped me understand that effective prompting requires more than asking a model to summarize text. A useful professional prompt needs a role, context, constraints, a clear output format, and rules for missing information.

The testing process also showed that a response may sound confident while still being unsupported. In healthcare administration, grounding and uncertainty are especially important. The final prompt performed better because it reduced ambiguity and made the output easier for staff to review and compare.

## AI Usage Disclosure

AI was used to support brainstorming, prompt development, formatting, and language improvement. I reviewed the project content, verified that all cases were fictional, and revised the wording to match the intended orthodontic administrative workflow.
