---
name: explain-to-me
description: Explains STAT 432 homework questions in plain language without solving them. Use only when the user explicitly asks to use the explain-to-me skill to read or explain a homework question.
disable-model-invocation: true
---

# explain-to-me

## Intent

Help the student understand what a homework question is asking. Clarify goals and required work. Do not complete derivations, write submission code, or give numerical answers.

## When to use

Apply this skill only when the user explicitly names `explain-to-me` or asks you to use this skill on a homework question.

## Instructions

1. Read the named question (from the student's file, pasted text, or `homework-NN.qmd`).
2. Respond in a short, friendly tone with:
   - **Goal**: What concept or method the question targets.
   - **Required work**: What to compute, derive, plot, or write (by part if applicable).
   - **Inputs and constraints**: Data, seeds, formulas, or conventions stated in the prompt.
   - **Lecture pointers**: Link to the most relevant Week 3 material when ridge-related:
     - [Ridge Regression: Stability Through Shrinkage](https://teazrq.github.io/stat432rpy/topics/ridge-regression/ridge-regression.html)
     - [From a Penalized Objective to a Fitted Ridge Model](https://teazrq.github.io/stat432rpy/topics/ridge-regression/optimization-and-cross-validation.html)
3. End with one sentence on how to start, without doing the work.

## Rules

- Do not write full solutions, code for submission, or final numeric results.
- Do not rewrite the student's answers or judge whether they are correct.
- If the user asks for the answer, remind them the skill is for understanding only and offer to clarify the question instead.
- Keep the explanation concise (roughly 150–300 words unless the user asks for more detail).
