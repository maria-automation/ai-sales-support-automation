# Architecture

## Main flow

Telegram Trigger -> Input validation -> Load customer history -> AI Agent -> JavaScript processing -> customer reply + manager notification + Google Sheets storage.

## Status flow

Manager Telegram action -> status selection -> Google Sheets update.

## Responsibility split
- AI: interpretation, classification, lead scoring and response generation.
- n8n: orchestration and routing.
- Google Sheets: demo customer history and lead state.
- Telegram: customer and manager interface.
