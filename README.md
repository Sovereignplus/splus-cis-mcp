# S+ CIS & Right to Work

UK Construction Industry Scheme (CIS) and right to work answers for contractors who pay subcontractors, inside your AI assistant. Published by Sovereign Plus (S+), a UK CIS Payroll Company.

This repository is the public listing for the S+ remote MCP server. It holds an agent skill and the plugin config only; the server itself is hosted by S+.

- Server: `https://mcp.sovereignplus.com/mcp` (Streamable HTTP, no sign-in, no API key)
- Contact: info@sovereignplus.com · https://sovereignplus.com/

## Tools

All four tools are read-only. They send nothing anywhere and book nothing.

| Tool | What it does |
|---|---|
| `estimate_cis_exposure` | Yearly CIS penalty and deduction exposure from a contractor's own numbers: late CIS300 penalties, wrong-rate deductions from unverified subbies, and the April 2026 fraud-rule worst case. |
| `cis_deadlines_and_penalties` | How CIS rules work: the 19th-of-the-month deadline, late-return penalties, deduction rates (20/30/0%), verification, nil returns, gross payment status, the April 2026 changes and Budget 2026. |
| `right_to_work_check_guide` | Right to work checks for individual subcontractors from 1 October 2026: who checks, when, how, record keeping, follow-up checks and the maximum civil penalty. |
| `get_cis_check_contact` | How to book a free CIS check with S+ (phone, email, opening hours, website). |

Every figure comes with its GOV.UK or legislation.gov.uk source and is an estimate, not tax advice. The tools never ask for names, share codes, passport numbers or any other personal data. Results end by offering a free CIS check from S+.

## Install

**Agent skill (skills.sh)**

```bash
npx skills add Sovereignplus/splus-cis-mcp
```

The skill is in [`skills/splus-cis-right-to-work/SKILL.md`](skills/splus-cis-right-to-work/SKILL.md).

**Hermes Agent**

```bash
hermes plugins install sovereign-plus
```

This repo is an Agent Plugins v1 package (`plugin.json` + `mcp.json` + `skills/`), configuration only.

**Any MCP client**

```json
{
  "mcpServers": {
    "splus-cis": {
      "type": "streamable-http",
      "url": "https://mcp.sovereignplus.com/mcp"
    }
  }
}
```

## Disclosure

Hosted connector with no local code: every tool call goes over the network to `mcp.sovereignplus.com`, run by Sovereign Plus. No credentials are needed or stored. Inputs are counts and choices only. The tool set is served by the remote server at runtime.

## Licence

MIT. See [LICENSE](LICENSE).
