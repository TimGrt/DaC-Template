# Pipeline

## Github Pages

Für einen automatischen Rebuild der Dokumentation in Github Pages durch Github Actions muss im Projekt-Hauptverzeichnis die Datei `.github/workflows` erstellt werden

```yaml
---
name: Deploy MkDocs to Github pages
on:
  workflow_dispatch:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-python@v2
        with:
          python-version: 3.x
      - run: pip3 install -r requirements.txt 
      - run: mkdocs gh-deploy --force
```

Hier wird bei jedem Push oder Pull-Request gegen den *main*-Branch (oder durch einen manuellen Trigger) die Pipeline ausgeführt.

## Gitlab

Eine mögliche Pipeline ausgeführt über einen Gitlab-Runner könnte folgendermaßen aussehen, die Datei muss als `.gitlab-ci.yml` im Projekt-Hauptverzeichnis hinterlegt sein:

```yaml
variables:
  GIT_STRATEGY: clone

stages:
  - build

Build and deploy:
  stage: build
  only:
    - master
    - web
  script:
    - 'echo -e "### Build new instance with Docker-compose. ###"'
    - 'docker-compose up -d --build'
  tags:
    - handbuch
```

Hier wird ein *docker-compose*-File angesprochen, in welchem der Image-Rebuild und Start eines Docker-Containers aus diesem Build definiert ist:

```yaml
version: "3.3"

services:
 web:
  build: .
  image: handbuch
  ports: 
    - "13000:80"
  restart: always
  container_name: betriebshandbuch

```