# API Contracts

> The contract between frontend, backend and AI modules. Agree on it **before** building. Any change needs a note to the whole team and a PR that updates this file.

## Conventions

- Base URL: `<fill in>`
- Content type: `application/json`
- Standard error shape (example, adjust if the team agrees on another):

```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Human-readable description",
    "details": {}
  }
}
```

---

## Endpoint Template

Copy this section for each endpoint.

### `<METHOD> <path>` — <short name>

**Purpose:** _what this endpoint does_

**Owner:** _developer name_

**Authentication:** _none / API key / bearer token / session — and required role_

**Request**

- Path / query parameters:

| Name | Type | Required | Description |
|------|------|----------|-------------|
|      |      |          |             |

- Body:

```json
{
}
```

**Success response** — status `200`

```json
{
}
```

**Error responses**

| Status | Code | When it happens |
|--------|------|-----------------|
| 400 | VALIDATION_ERROR | Invalid or missing input |
| 401 | UNAUTHENTICATED | Missing or invalid credentials |
| 403 | FORBIDDEN | Authenticated but not allowed |
| 404 | NOT_FOUND | Resource does not exist |
| 500 | INTERNAL_ERROR | Unexpected server error |

---

## Endpoint Index

| Method | Path | Purpose | Auth | Owner | Status (planned / built / tested) |
|--------|------|---------|------|-------|-----------------------------------|
|        |      |         |      |       |                                   |
