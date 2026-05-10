# authentik + caddy + paperless + outline

## Setup

1. `.env` anpassen: Domains und Secrets setzen.
2. DNS-A/AAAA Records auf den Host zeigen lassen.
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

- authentik: `https://${AUTHENTIK_HOST}`
- paperless: `https://${PAPERLESS_HOST}`
- outline: `https://${OUTLINE_HOST}`

## Authentik Blueprints

Die OIDC Provider und Applications für Paperless und Outline liegen unter:

```text
authentik/blueprints/apps.yaml
```

Die Datei wird in die authentik-Container nach `/blueprints/custom` gemountet.
