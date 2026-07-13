# Roadmap

Welcome to the development roadmap of **bn-bijoy-modern**.

This project aims to build a modern, Unicode-first Bangla input method for Linux using the m17n framework while preserving the familiar Bijoy keyboard layout and Windows-style typing behavior.

This roadmap documents the project's long-term vision, development phases, and future goals.

---

# Vision

The goal is not simply to create another Bangla keyboard layout.

The goal is to build a clean, maintainable and open-source Bangla input method that provides a native Windows Bijoy typing experience on Linux.

The project follows a simple philosophy:

* Keep the Bijoy keyboard layout.
* Modernize the typing behavior.
* Keep the implementation understandable.
* Design for future expansion.

---

# Guiding Principles

* Unicode First
* Documentation First
* Small Git Commits
* Backward Compatible Layout
* Open Source Friendly
* Community Driven
* Test Before Release

---

# Development Phases

## Phase 1 — Project Foundation

Goal:

Create the project structure and establish development guidelines.

Deliverables:

* Repository initialization
* Documentation
* Project license
* Development workflow
* Git conventions

Status:

✅ Completed

---

## Phase 2 — Typing Specification

Goal:

Define the typing rules independently from implementation.

This document becomes the project's source of truth.

Examples:

* Consonant + ি
* Consonant + ে
* Consonant + ৈ
* Ref
* Virama
* Conjunct formation

Deliverables:

* typing-specification.md

Status:

🚧 In Progress

---

## Phase 3 — Minimal m17n Prototype

Goal:

Create the smallest working input method.

Supported features:

* Basic consonants
* Independent vowels
* Dependent vowels
* Basic typing
* Installation on Linux

Success Criteria:

Users can install the keyboard and type simple Bangla text.

---

## Phase 4 — Windows-style Typing Engine

Goal:

Implement the Windows Bijoy typing experience.

Features:

* Type consonant first
* Type vowel sign after consonant
* Automatic Unicode ordering
* Pre-base vowel handling
* Composite vowel handling

Success Criteria:

Typing feels identical to Windows Bijoy.

---

## Phase 5 — Full Character Support

Goal:

Support every Bangla character.

Features:

* All consonants
* All vowels
* All dependent vowels
* Numbers
* Symbols
* Punctuation

---

## Phase 6 — Conjunct Engine

Goal:

Support Bangla conjunct characters.

Features:

* Virama
* Common conjuncts
* Rare conjuncts
* Automatic conjunct generation

Examples:

* ক্ষ
* ত্র
* ন্ত
* ক্ত
* গ্ধ

---

## Phase 7 — Advanced Typography

Goal:

Support advanced Bangla writing.

Features:

* Ref
* Reph
* Ya-phala
* Ra-phala
* Complex vowel combinations

---

## Phase 8 — Testing

Goal:

Ensure stability and correctness.

Tasks:

* Word list testing
* Sentence testing
* Regression testing
* Real-world typing tests

---

## Phase 9 — Documentation

Goal:

Provide complete project documentation.

Documents include:

* Installation Guide
* User Guide
* Developer Guide
* Contribution Guide
* Internal Architecture

---

## Phase 10 — Public Release

Goal:

Publish the first stable release.

Tasks:

* Version 1.0.0
* GitHub Release
* Release Notes
* Installation Packages

---

# Future Goals

After the m17n implementation reaches maturity, the project may expand to:

* Native IBus engine
* Fcitx5 support
* Wayland optimization
* GUI configuration tool
* Automatic installer
* Distribution packages
* Community-maintained dictionaries

These are long-term goals and are intentionally scheduled after the m17n implementation is stable.

---

# Contribution Philosophy

Every contribution should make the project:

* Easier to understand
* Easier to maintain
* Easier to test

Large changes should be divided into small reviewable commits whenever possible.

---

# Current Milestone

Current Focus:

**Phase 2 — Typing Specification**

The project is currently defining the typing rules that will serve as the foundation for every future implementation.

No implementation should contradict the typing specification.

---

> "A good input method is not measured by how many rules it contains, but by how natural it feels to the typist."
