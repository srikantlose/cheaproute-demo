# CheapRoute — Interactive Demo

Live: **https://cheaproute-demo.vercel.app/**

A single self-contained `index.html` (no build step, no backend) that visualizes the
results of CheapRoute's real 19-task evaluation run and lets you try the routing logic
yourself:

- **Route a query** — type any prompt and watch the actual classification heuristic and
  confidence-gate rules run live in your browser (ported verbatim from
  [`src/cheaproute/tasktype.py`](https://github.com/srikantlose/cheaproute-agent/blob/main/src/cheaproute/tasktype.py)
  and `config.yaml` in the main repo). Prompts matching one of the 19 evaluated tasks
  replay the real recorded route/confidence/answer; novel prompts get the real routing
  decision with no fabricated answer or confidence score — no model runs in-browser.
- **Charts & results table** — accuracy, routing split, and latency distribution across
  the 19-task run, with per-task drill-down (prompt, local/remote answers, confidence
  signals) and filter/sort controls.
- **τ (threshold) simulator** — drag the confidence threshold and see how the local/remote
  split would change, computed from each task's real recorded confidence.

All data is cached from an actual `docker run` of the submitted image against the
19-task practice set — this dashboard does not call any model or API.

## Run locally

Just open `index.html` in a browser — no server, no dependencies beyond two CDN-hosted
libraries (Chart.js, Google Fonts).

## Related

- Agent source + submission: [github.com/srikantlose/cheaproute-agent](https://github.com/srikantlose/cheaproute-agent)
- Docker image: `docker.io/srikantlose/cheaproute-agent:latest`
