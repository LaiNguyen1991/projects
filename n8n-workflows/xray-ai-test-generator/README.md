# Xray AI Test Cases Generator for n8n

Generate high-quality Xray test cases automatically from Jira Stories using AI and import them directly into Xray Cloud.

## Features

- Retrieve Jira Story details
- Read Acceptance Criteria and Technical Solution
- Search existing Xray Test Repository
- Reuse existing test flows to avoid duplication
- Generate AI-powered test cases
- Support Callable Test and Duplicate detection
- Import generated tests into Xray Cloud
- Automatically link generated tests back to the original Jira Story
- Optional UI image analysis for better UI validation

## Workflow

```
Input Form
    │
    ▼
Retrieve Jira Story
    │
    ▼
Normalize Story
    │
    ├──────────────► Get Existing Xray Tests
    │                    │
    ▼                    ▼
        Merge Context
              │
              ▼
 Compress Existing Tests
              │
              ▼
        AI Test Generator
              │
              ▼
   Convert to Xray Format
              │
              ▼
   Import Test Cases to Xray
```

---

## Requirements

- n8n
- Jira Cloud
- Xray Cloud
- Google Gemini API

## Configuration

Configure the following credentials before running the workflow.

### Jira

- Jira Base URL
- Email
- API Token

### Xray

- Client ID
- Client Secret

### Google Gemini

- Gemini API Credential

---

## Input

| Field | Description |
|--------|-------------|
| Project | Jira project key |
| Jira Story Issue | Jira issue key (e.g. PROJECT-123) |
| Xray Folder Path | Repository folder |
| Labels | Optional labels |
| UI Images | Optional screenshots |

---

## AI Coverage

The AI generates:

- Happy path
- Alternative flows
- Negative scenarios
- Boundary cases
- Validation checks
- End-to-end workflows
- Reusable Callable tests
- Duplicate detection

---

## Duplicate Prevention

Before creating new tests, the workflow:

1. Downloads existing Xray tests.
2. Resolves reusable call chains.
3. Compares repository coverage.
4. Reuses existing tests whenever possible.

This minimizes duplicated test cases.

---

## Security

This repository does **not** contain:

- Jira API Token
- Xray Client Secret
- Gemini API Key
- Personal credentials

Replace all placeholder credentials with your own before running the workflow.

---

## Notes

This workflow is intended for Xray Cloud.

The AI prompt has been optimized for generating reusable, repository-aware test cases while minimizing duplicate coverage.

## License

MIT
