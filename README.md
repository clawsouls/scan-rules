# SoulScan™ Rules

Open security rules used by [SoulScan](https://clawsouls.ai/soulscan) — the AI persona security scanner.

## What is SoulScan?

SoulScan scans AI agent persona packages (souls) for security vulnerabilities, prompt injections, and quality issues. It's used by the [ClawSouls](https://clawsouls.ai) registry to verify every published soul.

**Try it now:** [clawsouls.ai/soulscan](https://clawsouls.ai/soulscan)

## Stats

- **53 rules** across 6 categories
- **Version:** 1.2.0
- **Languages covered:** English, Korean, Japanese, Chinese, Spanish, French, German, Russian

## Rule Format

Each rule in `scan-rules.json` has the following fields:

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique rule identifier (e.g., `SEC001`) |
| `pattern` | string | Regex pattern to match against soul file content |
| `severity` | string | `error` or `warning` |
| `description` | string | Human-readable description of what the rule detects |
| `category` | string | Rule category (see below) |

### Categories

- **security** — Prompt injection, code execution, privilege escalation
- **secrets** — API keys, tokens, credentials
- **harmful** — Violence, hate speech, impersonation, fraud
- **social-engineering** — Credential harvesting, deception
- **xss** — Cross-site scripting, HTML injection
- **quality** — Content quality checks

## Contributing

We welcome new rules! To contribute:

1. Fork this repository
2. Add your rule to `scan-rules.json` following the existing format
3. Use a new sequential ID (e.g., `SEC054`)
4. Include a clear `description` explaining what the pattern catches
5. Test your regex pattern against real-world examples
6. Submit a PR with:
   - The new rule(s)
   - Example content that triggers the rule
   - Rationale for why this pattern is important

### Guidelines

- Patterns should have low false-positive rates
- Include multi-language patterns where applicable
- Error severity = definite security threat; Warning = potential concern
- Keep patterns focused — one concern per rule

## Usage

These rules are used by:

- **SoulScan Web** — [clawsouls.ai/soulscan](https://clawsouls.ai/soulscan)
- **ClawSouls CLI** — `npx clawsouls soulscan`
- **ClawSouls Registry** — automatic scanning on publish

## License

Apache-2.0 — see [LICENSE](LICENSE)

---

Soul Spec™ is a trademark of ClawSouls.
