# Architecture

> Fill this in after `problem-analysis-template.md`. Remove sections that do not apply. Record major choices in `decisions.md`.

## 1. High-Level Architecture

_Add a diagram (ASCII, Mermaid or image link) showing the main components and how they connect._

```text
[Client] <--> [Backend API] <--> [Database]
                   |
                   +--> [AI component] --> [External AI service]
```

## 2. Components

### Frontend
- Responsibility:
- Key screens / flows:
- State management:

### Backend
- Responsibility:
- Main modules / services:

### AI Components
- What the AI does (and what it does not):
- Model / provider:
- Inputs and outputs:
- Prompting / retrieval approach:
- Failure handling (timeouts, bad output, rate limits):
- Cost and latency considerations:

## 3. Database Design

- Database type and reason:
- Main entities and relationships:

| Entity | Key fields | Relationships |
|--------|------------|---------------|
|        |            |               |

- Migration / seed data approach:

## 4. External Services and APIs

| Service | Purpose | Auth method | Limits / cost | Fallback if unavailable |
|---------|---------|-------------|---------------|-------------------------|
|         |         |             |               |                         |

## 5. Data Flow

_Describe the path of the main request(s) from user action to final response._

1. User ...
2. Frontend sends ...
3. Backend ...
4. Response ...

## 6. Technology Choices and Justification

| Area | Choice | Why | Alternatives considered |
|------|--------|-----|-------------------------|
| Frontend |   |     |                         |
| Backend  |   |     |                         |
| Database |   |     |                         |
| AI       |   |     |                         |
| Hosting  |   |     |                         |

## 7. Deployment Architecture

- Environments (local / demo):
- Hosting for each component:
- How to deploy (steps or script):
- Environment variables and secrets handling:
- Monitoring / logs available during the demo:
- Fallback plan if the live deployment fails (e.g. local run, recorded demo):
