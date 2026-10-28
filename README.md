# Forge data repository (client template)

**Retired from the client path on Oct 28, 2026 (the flipped design):** a new
client has ONE private repository holding the engine and their records
together, made from Zevrant's private template, and never a separate data
repository. This public template stays only for older installs (Pat's) and
as history; nothing new is made from it.

This is the **public template** for one client's **data repository** (decided
Oct 21, 2026), published at github.com/zevrant-forge/forge-data-template.
The client makes their own private copy of it in one click
(**Use this template**, then **Create a new repository**, **Private**,
**Create repository from template**). Zevrant never touches the copy:
**Zevrant is never added to it.** It holds everything with dollar amounts or
holdings, so the client's money details never sit where Zevrant can see them.

This template itself holds nothing private: this README, the notices job,
a small `.gitignore` for Forge's temporary files, and empty folders. Nothing
else may be added to it (a test in the engine checks that). The client's own
copy gains the settings file at setup.

Forge's cloud runs (routines in the client's own Claude account) save here
after every run. Nothing in it should be edited by hand.

| Folder | What Forge keeps there |
| --- | --- |
| `settings.yaml` (a file) | The client's rules: written by Forge from each version the client confirms on their My rules page. Since Oct 27, 2026 it lives here, not in the code repository, so Zevrant cannot read a client's rules. The client's own Claude writes the first, "no rules yet" file at setup |
| `rules/versions/` | One record per confirmed version: the time in New York and the client's zone, the summary, the confirmations |
| `runs/` | One log per run, answer, control, check-in and Close all |
| `results/` | The message for the client after each morning run |
| `proposals/` | Each morning's numbered trades, the client's one answer, and what happened to each trade |
| `ledger/` | The Forge ledger: only what Forge itself bought and sold |
| `prices/` | Saved daily prices |
| `schedule/` | When each scheduled_buy started counting |
| `earnings/` | The day's earnings calendar, if an earnings key is set |
| `notices/` | The morning "trades are waiting" email: this repository's GitHub job (`.github/workflows/forge-notices.yml`) turns each notice into a GitHub issue that @mentions the client, so GitHub emails them, and closes it with the result. The setup's test email is a notice too |
| `outbox/` | Alerts after they are copied to the code repository's status branch (`outbox/sent/`). Alerts never contain money details |
| `replay/` | Historical replay results (operational checks only) |

When the client needs help with a problem, they share **one** log file at a
time, by choice. Keys never go here: they live only in the client's own
Claude cloud setup.
