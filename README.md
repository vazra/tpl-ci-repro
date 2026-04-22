# tpl-ci-test

Reproduction repo for two SimpleDeploy app templates whose HTTP probe
flaked under CI despite working locally via raw `docker compose up`:

- `n8n/` — n8n + Postgres
- `umami/` — Umami + Postgres

Rendered from the templates in [vazra/simpledeploy](https://github.com/vazra/simpledeploy)
with simpledeploy.* labels stripped and the endpoint port mapped to 18080.

CI runs each stack on ubuntu-latest, polls `http://127.0.0.1:18080/` for
up to 360s, dumps container logs on failure.
