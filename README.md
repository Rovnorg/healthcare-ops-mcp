# Rōvn Healthcare Operations MCP

[![Rōvn Healthcare Operations MCP connector](https://glama.ai/mcp/connectors/to.rovn/healthcare-ops-mcp/badges/score.svg)](https://glama.ai/mcp/connectors/to.rovn/healthcare-ops-mcp) [![mcptry](https://mcptry.com/badge/to.rovn/healthcare-ops-mcp)](https://mcptry.com/servers/to.rovn/healthcare-ops-mcp)

Public, zero-authentication, read-only Streamable-HTTP Model Context Protocol (MCP) server hosted by **Rōvn, Inc.** ([rovn.to](https://rovn.to), distinct from Rivon Health).

- **MCP Endpoint (Streamable HTTP):** `https://rovn.to/api/mcp`
- **Discovery Manifest:** `https://rovn.to/.well-known/mcp.json`
- **Official MCP Registry ID:** `to.rovn/healthcare-ops-mcp`
- **Agent Card:** `https://rovn.to/.well-known/agent-card.json`
- **Canonical AI Info:** `https://rovn.to/ai-info`
- **Authentication:** None (public federal datasets & public website documentation only)
- **Privacy Boundary:** Strictly zero patient PHI and zero stored user lookups.

## Quick Connect

### Claude Desktop / Cursor / Windsurf (`mcpServers`)

```json
{
  "mcpServers": {
    "rovn-healthcare-ops": {
      "url": "https://rovn.to/api/mcp"
    }
  }
}
```

### Direct JSON-RPC 2.0 Test (`curl`)

```bash
curl -sS -X POST https://rovn.to/api/mcp \
  -H "Content-Type: application/json" \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list","params":{}}'
```

## Available Read-Only Tools (`v1.1.0`)

| Tool | Description |
|---|---|
| `lookup_medicare_revalidation` | Live CMS November 2026 Medicare revalidation due dates, enrollment IDs, specialties, and group reassignment status by 10-digit NPI. |
| `lookup_nppes_provider` | Public CMS NPPES v2.1 legal name, alternate names, primary taxonomy, practice state, and matching state Medicaid exclusion links by 10-digit NPI. |
| `get_state_licensing_board` | Official RN/LPN licensing board, CNA nurse aide registry, Nurse Licensure Compact (NLC) status, and verification guides across 15 covered states (`GA, FL, TX, OH, NC, PA, VA, CA, NY, IL, MI, NJ, MA, TN, AZ`). |
| `compare_credentialing_platforms` | Dated November 2026 public-documentation comparison of Medallion, Verifiable, CertifyOS, Assured, symplr, and Rōvn. |
| `ask_rovn_healthcare_ops` | Deterministic grounded search across Rōvn's public healthcare credentialing guides, 15-state boards, CMS revalidation study, and comparisons. |
| `estimate_delayed_start_cost` | Transparent delayed-start agency-premium and delayed-billing arithmetic strictly from caller-supplied hiring and rate inputs. |
| `check_nlc_compact_status` | Nurse Licensure Compact (NLC) multistate vs single-state eligibility across all 50 U.S. states and DC. |
| `get_oig_exclusion_checklist` | Federal HHS OIG LEIE, SAM.gov, and state Medicaid exclusion screening checklist. |
| `get_snf_onboarding_checklist` | 4-track parallel skilled nursing facility (SNF) onboarding checklist under 42 CFR 483.12 & 483.156 separating portable clinician items from employer-fresh screening. |
| `get_healthcare_ai_benchmarks` | Dated 2025 to November 2026 primary-source healthcare AI adoption, buyer ROI hurdle, RN turnover, physician contract-to-start, and CMS Medicare revalidation benchmarks. |

## Available MCP Resources

- `rovn://llms.txt` — Machine-readable index of all public pages on `rovn.to`
- `rovn://ai-info` — Canonical entity profile, capabilities, pricing boundaries, and live endpoints
- `rovn://research/medicare-revalidation` — Aggregate November 2026 CMS Medicare revalidation study summary (`2,985,447` enrollments, `45,356` deadlines through Apr 30, 2027)
- `rovn://research/credentialing-software-matrix` — Six-vendor public comparison matrix

## About Rōvn

[Rōvn](https://rovn.to) is LinkedIn for healthcare with hands: an AI-native healthcare workforce operating system and source-checked clinician career network built to replace the 112-day contract-to-start wait with first shifts engineered in under 14 days while giving every facility private operating intelligence built strictly on data it owns and every clinician a free living record plus a 24/7 personal AI career advocate. Rōvn is software (not a staffing agency, employer of record, or payroll provider), and authorized healthcare leaders retain 100% of hiring, credentialing, privileging, and clinical decisions.

## License

MIT — see [LICENSE](./LICENSE).
