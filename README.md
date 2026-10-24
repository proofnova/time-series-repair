# Time-series repair

시간대·중복·누락·순서가 뒤섞인 계측 자료를 명시한 시간 격자로 정리한다.

A focused executable resource for AI-assisted structured work. **Zero runtime dependencies, no API key, Node.js 22+.**

[Live workspace](https://proofnova.github.io/time-series-repair/) · [한국어 리소스 모음](https://proofnova.github.io/) · [Task contract](resource.json) · [Prior art](RESEARCH.md)

```sh
git clone https://github.com/proofnova/time-series-repair.git
cd time-series-repair
npm test
node cli.mjs example.json
```

## What it does

Offset-aware timestamps, weighted buckets and explicit missing intervals.

Missing observations remain null, not zero; duplicate buckets retain their source rows.

## Connect a model

Import `execute` from `./run.mjs`. Expose this declared tool to your model, validate its tool name/input contract, execute it, and retain the returned JSON and input digest. Calculations and constraint checks are performed by the resource. No paid model or new agent framework is required.

[SKILL.md](SKILL.md) contains the workflow, interpretation and recovery procedure. [example.json](example.json) is a complete input; [cases.json](cases.json) contains worked and edge-case synthetic regression checks. The website executes the same code locally in a bounded Worker. It has no model or external data upload.

## Recovery and limits

Supply explicit offsets; correct rejected values; preserve gaps instead of inventing observations.

Underlying algorithms and task outcomes already exist in the alternatives. An existing tool configured for this exact task may remove the need for a separate project. Small synthetic tests cannot establish broad expertise or external demand. See [RESEARCH.md](RESEARCH.md). A plan/audit is not an external action or proof of actual user benefit.

## Contribute

Open an issue with a synthetic/redacted failing JSON input, expected result and Node version. Add a regression test and run `npm test`. Never include credentials or real private records in public examples.

MIT · Proofnova · 2026
