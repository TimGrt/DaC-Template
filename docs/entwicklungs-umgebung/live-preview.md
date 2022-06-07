# Live-Preview

Der eingebaute *Dev*-Server ermöglicht es die Dokumentation schon während des Schreibens in der Vorschau zu betrachten. Er lädt sogar automatisch neu und aktualisiert den Browser, wenn die Änderungen gespeichert werden.

## How-To

Python Virtual Environment erstellen:

```bash
pip3 -m venv mkdocs-venv
```

VE aktivieren:

```bash
source mkdocs-venv/bin/activcate
```

Requirements installieren:

```bash
pip3 install -r requirements.txt
```

IP-Adresse herausfinden:

```bash
hostname -I
```

MkDocs built-in dev-server für *live*-Preview starten:

```bash
mkdocs serve -a 172.26.220.226:8080
```