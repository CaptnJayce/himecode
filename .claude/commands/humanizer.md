---
name: humanizer
version: 2.5.1
license: MIT
compatibility: claude-code opencode
---

# Humanizer: Remove AI Writing Patterns

## Overview

Identify and remove AI-generated writing patterns to make text sound more natural and human. Based on Wikipedia's "Signs of AI writing" guide maintained by WikiProject AI Cleanup.

## Core Task

When humanizing text:

1. Scan for 29+ documented AI patterns
2. Rewrite problematic sections naturally
3. Preserve meaning and intended tone
4. Inject personality and voice
5. Conduct a final anti-AI audit

## Key Pattern Categories

**Content patterns:** Undue emphasis on significance, notability, superficial "-ing" analyses, promotional language, vague attributions, formulaic challenges sections

**Language patterns:** Overused "AI vocabulary" (crucial, tapestry, showcase, interplay), copula avoidance ("serves as" instead of "is"), negative parallelisms, rule-of-three overuse, passive voice

**Style patterns:** Em dash overuse, excessive boldface, inline-header lists, title-case headings, emojis, curly quotation marks

**Communication patterns:** Chatbot artifacts ("I hope this helps"), knowledge-cutoff disclaimers, sycophantic tone

**Filler/hedging:** Unnecessary qualifiers, excessive hedging, generic conclusions, hyphenated-pair uniformity, persuasive authority tropes, announcement phrases, fragmented headers

## Voice Calibration

Optionally match a user's writing sample by analyzing:
- Sentence length patterns
- Word choice level
- Paragraph openings
- Punctuation habits
- Transitions

Then replace AI patterns with patterns matching their voice.

## Adding Soul

Good writing requires personality beyond pattern-removal:
- Have opinions and reactions
- Vary sentence rhythm
- Acknowledge complexity and mixed feelings
- Use first person when appropriate
- Allow some natural imperfection
- Be specific about feelings

## Output Format

Present: draft rewrite → brief AI-pattern audit → final revised version → summary of changes
