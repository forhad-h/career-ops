# Mode: tracker — Application Tracker

Reads and displays `data/applications.md`.

**Tracker format:**
```markdown
| # | Date | Company | Role | Score | Status | PDF | Report |
```

Possible statuses: `Evaluated` → `Applied` → `Responded` → `Interview` → `Offer` / `Rejected` / `Discarded` / `SKIP`

- `Applied` = candidate submitted their application
- `Responded` = a recruiter/company reached out and candidate responded (inbound)
- `Interview` = candidate is in an active interview process

If the user asks to update a status, edit the corresponding row.

Also display statistics:
- Total applications
- By status
- Average score
- % with PDF generated
- % with report generated
