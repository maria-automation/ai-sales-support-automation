# AI Sales & Support Automation for an Online School

Demo portfolio project showing an AI-powered workflow for automating first-line customer communication and lead qualification.

## Business problem
Managers receive repetitive customer messages and need to identify which conversations deserve immediate attention. The system reduces routine manual work by classifying requests, scoring leads, using customer history and routing information to the manager.

## What the system does
- receives Telegram messages;
- retrieves previous customer interactions from Google Sheets;
- analyzes the current request with an AI Agent;
- classifies the request;
- assigns HIGH / MEDIUM / LOW lead priority;
- identifies the course and summarizes the request;
- generates a customer response;
- stores the interaction;
- notifies the manager;
- supports lead status updates through Telegram.

## Architecture

```text
Customer -> Telegram -> Validation -> Customer history -> AI Agent
                                             |
                                             v
                                  Structured AI result
                                             |
                                             v
                                      JavaScript
                                  /       |       \
                                 /        |        \
                         Customer reply Manager   Google Sheets
                                      notification    |
                                                     v
                                               Lead history
```

## AI layer
The AI Agent handles request classification, lead scoring, course identification, request summary and response generation.

Lead score:
- HIGH: strong buying intent / hot lead
- MEDIUM: meaningful product interest
- LOW: routine or low-priority request

Request types used by the workflow:
- Продажи
- Поддержка
- Возвраты
- Другое

## Customer history
Google Sheets acts as the demo data store. The workflow keeps Telegram user ID, username, date, course, request type, score, summary, original message, first contact date, interaction count and status.

## Manager workflow
The manager receives structured lead information in Telegram. A separate branch supports status changes such as Оплачено and Закрыто, which are written back to the data store.

## Tech stack
- n8n
- OpenAI GPT-4.1-mini
- Telegram Bot API
- Google Sheets
- JavaScript

## Repository
```text
ai-sales-support-automation/
├── README.md
├── workflows/
│   └── online-school-ai-automation-sanitized.json
├── docs/
│   ├── SETUP.md
│   ├── ARCHITECTURE.md
│   └── SECURITY.md
├── examples/
│   └── sample-lead.json
└── screenshots/
```

## Project status
Demo / Portfolio Project. This repository demonstrates workflow architecture and AI automation. It is not presented as a production deployment for a real client.
