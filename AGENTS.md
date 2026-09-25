# Claude Code Automation

## GitHub Issue → Jira Workflow

When a new GitHub issue is opened (`issues.opened` event):

1. **Classify** the issue as **Bug** or **Story** (Feature Request):
   - Bug: describes something broken, incorrect behavior, error, crash, unexpected output
   - Story: describes a new feature, improvement, or enhancement request

2. **Create a Jira ticket** in project `WA` on `leadingcompanions.atlassian.net`:
   - Issue type: `Bug` or `Story` (based on classification above)
   - Summary: the GitHub issue title
   - Description: link to the GitHub issue + original issue body
   - Cloud ID: `f7bbf02e-c650-4c17-8c47-7f2cbcae26cf`

3. **Post a confirmation comment** on the GitHub issue:
   - Language: detect and match the language of the issue author's text
   - Content: brief acknowledgment that the issue has been received
   - Last line: the Jira issue key only (e.g. `WA-1068`), no other text on that line

## Security

This is a public repository. Never commit secrets or credentials. If a reporter pastes a token,
API key, or other credential into an issue body, never repeat it back — not in the confirmation
comment, not in the Jira ticket description. Quote only the surrounding context and note that the
credential was omitted.
