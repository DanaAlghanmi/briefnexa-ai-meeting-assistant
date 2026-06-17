# Project overview

**Briefnexa** is a privacy-focused AI meeting assistant MVP that helps users turn meeting recordings into clear, structured, searchable meeting records.

The project was built as a practical product workflow, not just a transcription demo. The goal is to help users capture what happened in a meeting, understand the important points, and return to the meeting later without replaying the full audio.

## Problem

Meetings often contain valuable information, but the useful parts are easy to lose. A recording preserves the conversation, but it is time-consuming to review. A transcript is more accessible, but it still requires manual reading to find decisions, tasks, open questions, and risks.

This becomes even more important for bilingual users and Arabic-first teams. A meeting assistant should not assume that every workflow happens only in English or left-to-right interfaces.

## Who it is for

Briefnexa is designed for people who need a clear meeting record without manually writing everything during the call. This can include students, founders, project teams, operations teams, product teams, and professionals who regularly need to review decisions and follow-ups.

The MVP is especially useful for users who need:

- quick meeting summaries
- clear decisions and follow-ups
- action items with owners and due dates
- searchable meeting history
- meeting-specific questions and answers
- English and Arabic meeting workflows
- Arabic RTL interface support
- exportable or copyable meeting content

## What the MVP currently does

The current MVP supports the main meeting workflow end to end:

1. The user records a meeting in the browser or uploads audio.
2. Briefnexa processes the audio and generates a transcript.
3. The transcript is transformed into a structured meeting report.
4. The user reviews the executive summary, decisions, action items, open questions, risks, and transcript.
5. The user can ask questions about that specific meeting through Ask This Meeting.
6. The user can copy or export meeting content.
7. The user can search, filter, rename, or delete meetings from the dashboard.

## Privacy-first value proposition

Briefnexa treats raw audio as the most sensitive artifact in the workflow. After successful processing, the raw audio file is removed automatically. The transcript and structured report remain available because they are the artifacts users need for later review, search, and follow-up.

This privacy-oriented behavior is part of the product design, not an afterthought. Logs were also sanitized to avoid exposing signed URLs, storage keys, API keys, raw provider payloads, full transcripts, or private meeting content.

## Why bilingual support matters

Briefnexa is designed to support both English and Arabic meeting workflows, which is especially valuable for users and teams working in Arabic-first environments.

The current showcase demonstrates English meeting usage and Arabic usage, including RTL interface support, Arabic meeting report presentation, and Arabic Ask This Meeting. This makes the product more realistic for regional users who may switch between English and Arabic depending on the meeting, audience, or output format.

## Product thinking

The MVP focuses on three product principles:

1. **Useful outputs over raw AI output**
   The value is not just transcription. The value is turning meeting content into decisions, tasks, risks, questions, and reusable summaries.

2. **Meeting-specific intelligence**
   Ask This Meeting is scoped to a specific meeting so users can get targeted answers without mixing unrelated conversations.

3. **Bilingual usability**
   Arabic and English support is part of the product experience, including RTL handling and Arabic meeting outputs.
