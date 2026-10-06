# Optional In-App AI Feature Policy

> Rebuilt for v3. The original file was not available when this kit was edited.

In-app AI is optional. The rulebook allows it only under these conditions, and the default decision is **skip it** unless the main path, tests, bilingual UI, deliverables, and deployment are already complete and time remains (not before about T+60).

## Hard rules

- Main features must work fully without AI.
- The user types their own API key into the app. The key is never in source code, the repository, commit history, build output, screenshots, README, or the deployed site.
- Keep the key in memory (component state) by default. Do not write it to `localStorage`, URLs, or logs. If persistence is offered at all, make it opt-in and say so.
- No participant-controlled backend or proxy to hide a key.

## Design rules

- Tie AI to the actual workflow (for example "explain this result", "suggest a fix for this validation error"), not a generic chatbot.
- Send only the minimum needed data. Never send private data.
- Check the provider's documentation for direct browser/CORS support before committing to it. If direct browser calls are not supported, drop the feature.
- Timeout, cancel, and error states are visible. On failure show a short message in the active language and keep the app usable.
- Label AI output as AI-generated. Never present it as the authoritative result.
- Bangla and English both supported for the feature's own UI text.

## Before adding it, answer

1. Are all ledger MUST rows done and tested?
2. Does it add clear value to the judge's experience?
3. Can it be built and verified in under 10 minutes?
4. Does the app look and behave correctly when no key is entered?

If any answer is no, do not add it.

## README

If used, list it under bonus features and AI tools, state that the user supplies their own key, and state the known limits.
