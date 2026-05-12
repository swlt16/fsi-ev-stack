# authentik + caddy + paperless + outline + static site

## Setup

1. `.env` anpassen: Domains, HTTP-Port und Secrets setzen.
2. nginx mit SSL-Termination auf den HTTP-Port von Caddy weiterleiten lassen.
3. Starten:

```bash
docker compose up -d
```

## Secrets generieren

```bash
openssl rand -base64 60
openssl rand -hex 32
```

## Dienste

- authentik: `http://${AUTHENTIK_HOST}`
- paperless: `http://${PAPERLESS_HOST}`
- outline: `http://${OUTLINE_HOST}`
- static site: `http://${STATIC_HOST}`

Die statische Seite liegt unter:

```text
static/index.html
```

## Authentik Blueprints

Die OIDC Provider und Applications für Paperless und Outline liegen unter:

```text
authentik/blueprints/apps.yaml
```

Die Datei wird in die authentik-Container nach `/blueprints/custom` gemountet.
