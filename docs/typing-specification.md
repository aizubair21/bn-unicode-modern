# Typing Specification

Version: 0.1 (Draft)

---

## 1. Introduction

This document defines the official typing behavior of **bn-bijoy-modern**.

The purpose of this specification is to describe **how users interact with the keyboard**, independent of how the input method is implemented.

This specification serves as the single source of truth for the project.

Every implementation—including the m17n input method, future IBus engines, testing tools, and documentation—must follow the rules defined in this document.

Implementation details may change over time, but the typing behavior described here should remain stable unless a new version of this specification is published.

---

## 2. Purpose

The primary goal of this project is to provide a modern Unicode Bangla typing experience on Linux while preserving the familiar Bijoy keyboard layout and Windows-style typing behavior.

Users should be able to type Bangla naturally without needing to understand Unicode character ordering.

The input method is responsible for producing valid Unicode text.

---

## 3. Project Philosophy

The project follows four simple principles.

### 3.1 Unicode First

All output produced by the input method must be valid Unicode.

No proprietary encoding will be supported.

---

### 3.2 Familiar Typing

Users who previously used Windows Bijoy should feel immediately familiar with the typing experience.

The keyboard should adapt to the user—not the other way around.

---

### 3.3 Simple Implementation

Whenever multiple implementation approaches are possible, the simplest maintainable solution should be preferred.

Complex solutions should only be introduced when they provide a clear long-term benefit.

---

### 3.4 Documentation Before Code

Every typing behavior should be documented before it is implemented.

Documentation defines the expected behavior.

Implementation follows the documentation.

---

## 4. Scope

This specification defines:

- Typing behavior
- Character composition rules
- Unicode output rules
- Keyboard behavior
- Expected user experience

This specification does not define:

- Spell checking
- Dictionary support
- Auto correction
- Word prediction
- Keyboard themes
- Graphical configuration

These features may be added in future projects but are outside the scope of this specification.

---

## 5. Terminology

Throughout this document the following terms are used.

| Term | Meaning |
|-------|---------|
| Character | A Bangla Unicode character |
| Consonant | A Bangla consonant letter |
| Independent Vowel | A standalone vowel |
| Dependent Vowel | A vowel sign (কার) attached to a consonant |
| Virama | The Bangla hasanta (্) |
| Conjunct | A combination of multiple consonants |
| Ref | The leading form of র্ |
| Input Sequence | The order in which keys are pressed |
| Output | The Unicode text produced by the input method |

---

## 6. Rule Format

Every typing rule defined in this specification follows the same format.

Rule Number

Purpose

Input Sequence

Expected Output

Notes (optional)

Example:

RULE-001

Purpose

Insert a consonant.

Input

ক

Output

ক

Notes

The consonant is inserted immediately.