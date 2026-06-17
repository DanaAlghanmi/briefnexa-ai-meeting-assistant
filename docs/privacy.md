# Privacy approach

Briefnexa was designed with privacy-aware handling of meeting artifacts. This document explains the product decisions at a high level and avoids legal or compliance claims.

## Raw audio is treated as the most sensitive artifact

Raw meeting audio can contain voices, names, business context, private discussion details, and information that may not be needed after processing. For that reason, Briefnexa treats raw audio as the most sensitive artifact in the workflow.

## Private storage

Uploaded and recorded audio is stored privately during processing. The MVP avoids public access to raw meeting audio and does not rely on exposing storage paths directly to users.

## Signed server-side access for processing

Processing is handled through controlled server-side access. The server accesses the required audio file for transcription without exposing storage keys, API keys, or long-lived public file access.

## Raw audio auto-deletion

After processing completes successfully, the raw audio file is automatically removed. This reduces the amount of sensitive data retained by the product after the transcript and report have been generated.

## Transcript and report retention

The transcript and structured report remain available to the user because they are the core product value. They allow the user to review the meeting, search meeting content, ask questions, copy summaries, export reports, and revisit decisions or action items later.

## Delete meeting behavior

When a user deletes a meeting, the meeting data and transcript are removed from the application experience. The intent is to make deletion clear and user-controlled.

## Sanitized logs

Logs were sanitized to avoid exposing sensitive processing details. The MVP avoids logging:

- signed URLs
- storage keys
- API keys
- raw provider payloads
- full transcripts
- private meeting content

## No legal or compliance claims

This repository does not claim that Briefnexa is HIPAA, GDPR, SOC 2, or enterprise compliance certified. The privacy decisions described here are product and engineering decisions for an MVP and case study.
