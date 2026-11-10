# AI Agents Configuration Hub (`.agents`)

The `.agents/` directory is the Bounded Context for AI behavior customization, tool integration, and knowledge routing within the `org-ecosystem` product portfolio meta-repository.

---

## Architecture & Integration

Our AI agent configuration consumes sovereign domain plugins via the `@tupynambalucas-dev/agent-mesh` umbrella package:

### 1. Plugin Discovery Manifest (`plugins.json`)

```json
{
  "entries": [
    {
      "path": "commercial/omnichannel/node_modules/@tupynambalucas-dev/agent-mesh/plugins/packages"
    }
  ]
}
```

All 10 domain plugins (`appsheet`, `atelier`, `docusaurus`, `github-flow`, `github-org`, `gwork`, `repo`, `research`, `secrets`, `web`) and 8 sovereign MCP servers are discovered simultaneously via the installed package in `omnichannel`.

### 2. Sovereign MCP Launchers

MCP servers bundled in `@tupynambalucas-dev/agent-mesh` execute via self-contained launchers (`scripts/launcher.cjs`) without requiring external path resolutions.

---

## Directory Layout

- [plugins.json](./plugins.json): Runtime plugin discovery manifest.
- [AGENTS.md](./AGENTS.md): Bounded context router for `.agents/`.

---

## Navigation

- Parent Workspace: [Org-Ecosystem Meta-Repository Root](../README.md)
