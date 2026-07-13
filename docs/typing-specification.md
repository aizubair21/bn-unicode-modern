# Typing Specification

Version: 0.1

---

## Table of Contents

1. [Introduction](#1-introduction)
2. [Purpose](#2-purpose)

3. [Basic Typing Rules](#3-basic-typing-rules)
   - [RULE-001 Character Order](#rule-001--character-order)
   - [RULE-002 Consonants](#rule-002--consonants)
   - [RULE-003 Independent Vowels](#rule-003--independent-vowels)
   - [RULE-004 Dependent Vowel Signs](#rule-004--dependent-vowel-signs)
   - [RULE-005 No Unicode Knowledge Required](#rule-005--no-unicode-knowledge-required)
   - [RULE-006 Immediate Feedback](#rule-006--immediate-feedback)
   - [RULE-007 Invalid Combinations](#rule-007--invalid-combinations)
   - [RULE-008 Predictable Behavior](#rule-008--predictable-behavior)

4. [Dependent Vowel Rules](#4-dependent-vowel-rules)
   - [RULE-101 AA Kar (া)](#rule-101--AA-kar-)
   - [RULE-102 I Kar (ি)](#rule-102--i-kar-)
   - [RULE-103 II Kar (ী)](#rule-103--ii-kar-)
   - [RULE-104 U Kar (ু)](#rule-104--u-kar-)
   - [RULE-105 UU Kar (ূ)](#rule-105--uu-kar-)
   - [RULE-106 Vocalic R Sign (ৃ)](#rule-106--vocalic-r-sign-)

5. [Pre-base Vowel Rules](#5-pre-base-vowel-rules)
   - RULE-201 E Kar (ে)
   - RULE-202 AI Kar (ৈ)

6. [Composite Vowel Rules](#6-composite-vowel-rules)
   - RULE-301 O Kar (ো)
   - RULE-302 AU Kar (ৌ)

7. [Virama Rules](#7-virama-rules)

8. [Conjunct Rules](#8-conjunct-rules)

9. [Ref Rules](#9-ref-rules)

10. [Ya-phala Rules](#10-ya-phala-rules)

11. [Punctuation Rules](#11-punctuation-rules)

12. [Examples](#12-examples)

13. [Test Cases](#13-test-cases)

14. [Appendix](#14-appendix)



---

# Introduction

This document defines the official typing behavior of **bn-bijoy-modern**.

The purpose of this specification is to describe **how users interact with the keyboard**, independent of how the input method is implemented.

This specification serves as the single source of truth for the project.

Every implementation—including the m17n input method, future IBus engines, testing tools, and documentation—must follow the rules defined in this document.

Implementation details may change over time, but the typing behavior described here should remain stable unless a new version of this specification is published.

---

# Purpose

The primary goal of this project is to provide a modern Unicode Bangla typing experience on Linux while preserving the familiar Bijoy keyboard layout and Windows-style typing behavior.

Users should be able to type Bangla naturally without needing to understand Unicode character ordering.

The input method is responsible for producing valid Unicode text.


---

# Basic Typing Rules

This chapter defines the fundamental behavior of the input method.

Every implementation must follow these rules exactly.

---

## RULE-001 — Character Order

### Purpose

The input method shall process characters in the exact order they are typed by the user.

The engine may internally reorder Unicode characters when necessary, but the user shall never be required to type Unicode order manually.

### Example

User Types:

ক
ি

Displayed Output:

কি

---

## RULE-002 — Consonants

### Purpose

Typing a consonant inserts that consonant immediately.

### Examples

Input

ক

Output

ক

---

Input

গ

Output

গ

---

Input

ত

Output

ত

---

Notes

A consonant does not wait for future input before being displayed.

---

## RULE-003 — Independent Vowels

### Purpose

Typing an independent vowel inserts that vowel immediately.

### Examples

Input

অ

Output

অ

---

Input

আ

Output

আ

---

Input

ই

Output

ই

---

Notes

Independent vowels are complete letters.

They are not combined with previous consonants.

---

## RULE-004 — Dependent Vowel Signs

### Purpose

Dependent vowel signs (কার) modify the immediately preceding consonant.

Users type the consonant first, followed by the vowel sign.

The input method shall produce valid Unicode output.

### Example

Input

ক
া

Output

কা

---

Input

ক
ি

Output

কি

---

Input

ক
ে

Output

কে

---

Notes

The user always types naturally.

The engine is responsible for generating the correct Unicode sequence.

---

## RULE-005 — No Unicode Knowledge Required

### Purpose

Users are not expected to understand Unicode character ordering.

Typing behavior must follow normal Bangla writing habits.

The engine performs all necessary Unicode adjustments automatically.

### Example

Correct User Input

ক
ে

Correct Output

কে

The user is never required to type:

ে
ক

---

## RULE-006 — Immediate Feedback

### Purpose

Every valid key press should produce immediate visual feedback whenever possible.

Users should feel that they are typing naturally.

The input method may update previously inserted characters if required to produce correct Unicode text.

Example

User Types

ক

Screen

ক

User Types

ে

Screen Updates

কে

---

## RULE-007 — Invalid Combinations

### Purpose

If a character cannot legally combine with the previous character, it should be inserted as an independent Unicode character whenever possible.

The input method should avoid silently discarding user input.

Notes

Future versions may define more detailed error-handling behavior.

---

## RULE-008 — Predictable Behavior

### Purpose

The same input sequence must always produce the same output.

Typing behavior must never depend on application-specific behavior or font rendering.

This ensures consistent typing across all supported Linux applications.



------


# 4. Dependent Vowel Rules

This chapter defines the behavior of dependent vowel signs (কার) that are applied to the preceding consonant.

Unless otherwise specified, users shall always type the consonant first, followed by the dependent vowel sign.

The input method is responsible for producing valid Unicode output.

---

## RULE-101 — AA Kar (া)

### Purpose

The AA Kar extends the inherent vowel of the preceding consonant.

### Typing Behavior

The user types:

Consonant → AA Kar

### Expected Output

The input method shall attach the AA Kar to the immediately preceding consonant.

### Examples

| Input | Output |
|--------|--------|
| ক + া | কা |
| গ + া | গা |
| ন + া | না |
| ম + া | মা |

### Notes

No character reordering is required.

---

## RULE-102 — I Kar (ি)

### Purpose

The I Kar represents the short "i" vowel.

### Typing Behavior

The user types:

Consonant → I Kar

### Expected Output

The input method shall produce the correct Unicode sequence while displaying the vowel in its proper visual position.

### Examples

| Input | Output |
|--------|--------|
| ক + ি | কি |
| গ + ি | গি |
| ম + ি | মি |
| স + ি | সি |

### Notes

Although the vowel sign is visually rendered before the consonant in most fonts, the user always types it after the consonant.

The input method handles any required Unicode ordering.

---

## RULE-103 — II Kar (ী)

### Purpose

The II Kar represents the long "ī" vowel.

### Typing Behavior

The user types:

Consonant → II Kar

### Expected Output

The input method shall attach the II Kar to the preceding consonant.

### Examples

| Input | Output |
|--------|--------|
| ক + ী | কী |
| গ + ী | গী |
| ন + ী | নী |
| ম + ী | মী |

### Notes

The user never types the vowel sign before the consonant.

---

## RULE-104 — U Kar (ু)

### Purpose

The U Kar represents the short "u" vowel.

### Typing Behavior

The user types:

Consonant → U Kar

### Expected Output

The input method shall attach the U Kar below the preceding consonant.

### Examples

| Input | Output |
|--------|--------|
| ক + ু | কু |
| গ + ু | গু |
| ত + ু | তু |
| ম + ু | মু |

### Notes

No character reordering is required.

---

## RULE-105 — UU Kar (ূ)

### Purpose

The UU Kar represents the long "ū" vowel.

### Typing Behavior

The user types:

Consonant → UU Kar

### Expected Output

The input method shall attach the UU Kar below the preceding consonant.

### Examples

| Input | Output |
|--------|--------|
| ক + ূ | কূ |
| গ + ূ | গূ |
| ম + ূ | মূ |
| ন + ূ | নূ |

### Notes

No character reordering is required.

---

## RULE-106 — Vocalic R Sign (ৃ)

### Purpose

The Vocalic R Sign represents the vowel sound "ṛ".

### Typing Behavior

The user types:

Consonant → Vocalic R Sign

### Expected Output

The input method shall attach the vowel sign to the preceding consonant.

### Examples

| Input | Output |
|--------|--------|
| ক + ৃ | কৃ |
| গ + ৃ | গৃ |
| ত + ৃ | তৃ |

### Notes

Support for this vowel sign is required for complete Unicode compliance, even though it is used less frequently in modern Bangla writing.





--- 


# 5. Pre-base Vowel Rules

This chapter defines the behavior of pre-base dependent vowel signs.

Unlike other dependent vowels, these vowel signs are visually rendered before the consonant in most Bangla fonts.

However, users shall always type the consonant first, followed by the vowel sign.

The input method is responsible for producing valid Unicode output.

---

## RULE-201 — E Kar (ে)

### Purpose

The E Kar represents the vowel sound "e". Although it is visually displayed before the consonant, users type it after the consonant.

### Typing Behavior

User Input

Consonant → E Kar

The user shall never be required to type the vowel sign before the consonant.

### Expected Output

The input method shall produce the correct Bangla syllable.

### Examples

| Input | Output |
|--------|--------|
| ক + ে | কে |
| গ + ে | গে |
| ত + ে | তে |
| ন + ে | নে |
| ম + ে | মে |

---

## RULE-202 — AI Kar (ৈ)

### Purpose

The AI Kar represents the vowel sound "oi". Like E Kar, it is visually rendered before the consonant while being typed after it.

### Typing Behavior

User Input

Consonant → AI Kar

### Expected Output

The input method shall produce the correct Bangla syllable.

### Examples

| Input | Output |
|--------|--------|
| ক + ৈ | কৈ |
| গ + ৈ | গৈ |
| ন + ৈ | নৈ |
| ম + ৈ | মই |

---

## Design Notes

The visual position of a vowel sign does not determine the typing order.

Typing order is always determined by natural writing habits. Rendering is determined by the Unicode text produced by the input method and the rendering engine used by the operating system.