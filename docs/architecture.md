# Architecture

This document describes the high-level architecture of Briefnexa without exposing private source code or implementation details.

## High-level flow

```text
Browser recording or audio upload
        ↓
Upload for processing
        ↓
Private storage
        ↓
Signed server-side access
        ↓
Groq Whisper transcription
        ↓
Structured report generation with Groq LLM
        ↓
Database storage
        ↓
Meeting detail UI
        ↓
Ask This Meeting, export, copy, search, rename, delete
```

## System overview

Briefnexa starts in the browser. A user can record a meeting directly or upload an audio file. The audio is then sent through a server-side processing flow instead of being handled entirely on the client.

The system stores the uploaded audio privately for processing, then uses controlled server-side access to send it through transcription. Once the transcript is produced, the transcript is passed into a structured report generation step. The generated meeting record is then stored and made available in the user interface.

## Core components

### Browser recording and upload

The user-facing app supports recording a meeting from the browser and uploading audio for processing. The interface is designed to make the capture flow simple and to clearly communicate processing status.

### Private storage

Audio is stored privately during processing. Raw audio is treated as the most sensitive artifact because it can contain full meeting context, voices, and potentially sensitive discussion details.

### Transcription

The transcription step uses Groq Whisper to convert the meeting audio into text. The transcript becomes the foundation for the structured report and the meeting-specific Ask experience.

### Structured report generation

A Groq LLM is used to transform the transcript into a meeting report with practical sections, including summary, decisions, action items, open questions, and risks.

### Database storage

The processed meeting data is stored in Supabase Postgres. This includes meeting metadata, transcript text, generated report content, and the information needed for the dashboard and meeting detail views.

### Meeting detail UI

The meeting detail page presents the transcript, structured report, summary, decisions, action items, open questions, and risks in a readable format. It also supports copy and export actions.

### Ask This Meeting

Ask This Meeting lets the user ask questions about one specific meeting. This supports workflows such as follow-up email generation and formal Arabic minutes without requiring the user to manually scan the full transcript.

## Privacy-aware processing

After successful processing, the raw audio file is automatically removed. The transcript and report remain available because they are the main user-facing outputs.

## Scope of this document

This document is intentionally high-level because the source code is private. It explains the product architecture and design decisions without sharing backend code, frontend source files, database migrations, credentials, signed URLs, or provider payloads.
