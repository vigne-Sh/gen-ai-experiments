# gen-ai-experiments

Random exploration with gen-AI. This repo doubles as a **Claude plugin marketplace**.

## Plugins

| Plugin | What it does |
|---|---|
| [`vignesh-gen-ai-factory`](plugins/vignesh-gen-ai-factory) | A growing collection of skills. Currently: `indian-law-factory` — explains Indian law (BNS/BNSS/BSA, IPC/CrPC), how to read sections and case judgments, official legal sources, and Tamil Nadu grievance and legal-aid channels (CM Helpline, TNSLSA, 181). |

## Install

In Claude Code or Cowork:

```
/plugin marketplace add vigne-Sh/gen-ai-experiments
/plugin install vignesh-gen-ai-factory@gen-ai-experiments
```

Then use the law skill with `/vignesh-gen-ai-factory:indian-law-factory` or just ask an Indian-law question.

## Disclaimer

`indian-law-factory` provides general legal information, **not legal advice**. It is not a substitute for a licensed advocate. Laws, helpline numbers and contact details change; verify them on official sources before relying on them. Free legal aid is available through the Legal Services Authorities (NALSA 15100).

## License

MIT, see [LICENSE](LICENSE).
