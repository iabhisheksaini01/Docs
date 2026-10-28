
## 1. Scope Clarification

This document lists the entities and functionality described in the migration coverage summary. Some steps are delegated to external CLI commands, while others are implemented directly in the notebook. “Attempted,” “configured,” or “command executed” should not be interpreted as proof of successful migration; validate the destination GitHub repository and integrations after migration.
"""

## 2. GitLab → GitHub Migration Coverage

| # | Entity / Functionality | Notebook Method | Coverage |
|---:|---|---|---|
| 1 | Repository | `gh gl2gh migrate-repo` | Migration command |
| 2 | Git commit history | `gh gl2gh migrate-repo` | Migration command |
| 3 | Branches | `gh gl2gh migrate-repo` | Migration command |
| 4 | Git tags | `gh gl2gh migrate-repo` | Migration command |
| 5 | Issues | `gh gl2gh migrate-repo` | Migration command |
| 6 | Merge Requests → Pull Requests | `gh gl2gh migrate-repo` | Migration command |
| 7 | Labels | `gh gl2gh migrate-repo` | Migration command |
| 8 | Milestones | `gh gl2gh migrate-repo` | Migration command |
| 9 | Releases | `gh gl2gh migrate-repo` | Migration command |
| 10 | Release assets | `gh gl2gh migrate-repo` | Migration command; verify destination |
| 11 | Git LFS objects | `git lfs fetch --all`, `git lfs push --all` | Explicit transfer step |
| 12 | Repository topics | GitLab API + `gh repo edit --add-topic` | Explicitly handled |
| 13 | Project CI/CD variables → GitHub repository secrets | GitLab API + `gh secret set` | Attempted; partial limitations |
| 14 | Project webhooks | GitLab API + GitHub API | Re-created disabled |
| 15 | Webhook event mapping | `EVENT_MAP` in Python | Explicit mapping |
| 16 | Project snippets → GitHub Gists | GitLab API + `gh gist create` | Content conversion attempted |
| 17 | GitLab CI/CD pipeline → GitHub Actions workflow | `gh actions-importer migrate gitlab` | Conversion attempted |
| 18 | Mannequin identity mapping | `gh gei generate-mannequin-csv` | CSV generation |
| 19 | Mannequin identity reclaim | `gh gei reclaim-mannequin` | Command executed |
| 20 | Target repository visibility | `VISIBILITY = "private"` + migration command | Configured |
| 21 | GitLab project ID and topics retrieval | GitLab Projects API | Metadata retrieval, not full project metadata migration |
