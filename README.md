# FOINIK ~ AI Security Posture Mapper

A free, client-side tool that maps your AI system's architecture and tells you which real attack vectors apply to it , with mitigations and cross-framework references. No installs, no accounts, no telemetry.


## Why

Most AI security checklists are generic. FOINIK isn't a checklist , it's a small rules engine. You tell it what your system actually looks like (deployment model, interface, data sensitivity, and the specific components you use — RAG, agents, tool calling, MCP servers, code execution, etc.), and it works out which of 21 real threat vectors apply to *that* architecture, not a hypothetical one.

## How it works

1. **Set your system profile** ~ deployment, interface, data sensitivity, model type.
2. **Stage your components** ~ pick the pieces your system actually has, across entry, model, data, action, output, and infrastructure layers. They appear as connected nodes on a live architecture map.
3. **Run the scan** ~ a deterministic rules engine matches your staged components against 21 threat vectors and returns a risk score, severity breakdown, and per-vector mitigations.
4. **Export the result** ~ copy or download the full assessment as a Markdown report.

There's no AI, no backend, and no black box: the whole matching logic is one small readable function in `index.html` — every rule, every component, and every reference is plainly visible in the source.

## Frameworks referenced

Every identified vector is cross-mapped to:

- **OWASP Top 10 for LLM Applications** (2025)
- **MITRE ATLAS**
- **NIST AI RMF**
- **Google SAIF**
- **EU AI Act**
- **CWE**

## Privacy

Everything runs in your browser. Nothing you stage, scan, or export is sent anywhere. The only network request the page makes is loading two web fonts from Google Fonts — no analytics, no telemetry, no accounts.

## Running it locally

It's a single static HTML file. Either:

```bash
open index.html          # macOS
# or just double-click it
```

or serve it with any static server:

```bash
python3 -m http.server 8000
```

## Deploying

1. Push `index.html` to the root of a GitHub repo (or a `/docs` folder).
2. **Settings → Pages → Source → Deploy from branch → `main` / root.**
3. Live at `https://<username>.github.io/<repo>/` within a couple of minutes.

## Disclaimer

FOINIK is an educational aid to help you reason about your AI system's attack surface — it is not a substitute for a professional security review or penetration test.

## License

MIT , do whatever you'd like with it.
