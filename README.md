# docs-coru-dev

Documentation portal for **[Koru](https://www.coru.dev)** — the open-source
autonomous refactor loop. Served at **[docs.coru.dev](https://docs.coru.dev)**.

Single self-contained page (no build, no CDN): quickstart, the autonomous
loop, execution lanes (external IDE / vendor CLI via tillm / headless LLM via
OpenRouter or local endpoints), tickets & planfile, quality gates, dashboard,
CLI + env reference, troubleshooting, FAQ. Shared design system with
coru.dev and about.coru.dev (SVG icon sprite, fluid uniform type scale).

## Develop

```bash
xdg-open index.html
```

## Deploy

```bash
rsync -az index.html coru@coru.dev:docs.coru.dev/
```

## Related

- [www.coru.dev](https://www.coru.dev) · [about.coru.dev](https://about.coru.dev)
- [semcod/koru](https://github.com/semcod/koru) · [PyPI: koru](https://pypi.org/project/koru/)
