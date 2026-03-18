# One-Transport — General Claude Rules

## Organisation

- **Company:** One Transport (1TPT)
- **GitHub Org:** https://github.com/One-Transport

## Jira

- **Site:** https://onetransport.atlassian.net
- **Cloud ID:** `10597bc4-bc92-4851-8c09-d4cf66d434b4`
- **Primary project:** `TPO` — 1TPT Portal (Epic, Story, Task, Bug, Sub-task)
- **Other projects:** `BS` — board.sg, `ON` — OneDrive

When referencing Jira issues, use the `TPO-XXX` format. Use the Atlassian MCP tools to read/create/update issues.

**Jira ticket titles must always be prefixed with the app name:** `[App Name] <description>`

Example: `[Driver App] Add push notification support`

### Jira transition IDs (TPO project)

| Status      | Transition ID |
| ----------- | ------------- |
| In Progress | `31`          |
| Review      | `51`          |
| For Test    | `61`          |
| Done        | `41`          |

## Git Workflow

**Always follow these steps in order:**

1. Move the Jira ticket to **In Progress** (transition ID: `31`) using the Atlassian MCP
2. Create a branch from `main` — `git checkout main && git pull && git checkout -b <type>/TPO-XXX-short-description`
3. Write the code
4. Commit with format: `type: TPO-XXX description`
5. Push the branch — `git push -u origin <branch-name>`
6. Open a PR to `main` via `gh pr create`
7. Add the PR link as a comment on the Jira ticket using the Atlassian MCP
8. Move the Jira ticket to **Review** (transition ID: `51`) using the Atlassian MCP

**Never commit directly to `main`.**

### Branch naming

All branches must reference the Jira issue key:

```
<type>/TPO-XXX-short-description
```

Examples:

- `feat/TPO-940-add-recaptcha-login`
- `fix/TPO-123-location-not-updating`
- `refactor/TPO-456-assignment-list-cleanup`

Types: `feat`, `fix`, `refactor`, `chore`, `docs`
