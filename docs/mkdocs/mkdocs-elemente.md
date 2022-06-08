# Spezielle Elemente in MkDocs-Material

Das Material-Theme ist eines der beliebtesten Themes für MkDocs und bringt einige Erweiterungen für die visuell ansprechene Gestaltung eurer Dokumentation mit. 
Eine vollständige Übersicht inklusive Codebeispielen findet sich [hier](https://squidfunk.github.io/mkdocs-material/reference/), einige Highlights haben wir auf dieser Seite eingebaut.

# Admonitions

Admonitions, auch _Call-Outs_ genannt, sind eine gute Wahl um zusätzliche Inhalte einzufügen, ohne den Dokumentfluss wesentlich zu unterbrechen. MkDocs bietet mehrere verschiedene Arten von Admonitions und ermöglicht Verschachtelung beliebiger Inhalte.

???+ success annotate "Admonition"

      Es gibt eine große Anzahl (1) [Typen von Admonitions](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#supported-types), die alle häufigen Nutzungszwecke abdecken - zum Beipiel `alert`, `warning`, `info` und `success`.(2)

1:    :man_raising_hand: Die [MKDocs Material-Dokumentation](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#supported-types) ist sehr gut geschrieben und enthält viele Beispiele für Admonitions
2:    Diese Anmerkungen lassen sich ebenfalls sehr leicht in Markdown schreiben und integrieren.

# Codeblöcke

Auch Codeblöcke lassen sich sehr einfach einfügen und werden automatisch mit einem _Kopieren_-Button versehen.

```py
import tensorflow as tf
```
Wenn zu Beginn des Codeblocks die entsprechende Codesprache angegeben wird ergänzt MkDocs farbliche passende Syntax-Highlights.

```yaml
site_name: CC Documentation as Code Template
copyright: Copyright &copy; Computacenter 2022
```

# Tabs

Besonders praktisch für die Darstellungen von Code für verschiedene Umgebungen oder leicht abweichende Befehle eignet sich der Einsatz von Tab-Bars:

=== "RHEL"

     ```
     yum install python3-pip -y
     ```

=== "Ubuntu"

     ```
     $ sudo apt install python3-pip
     ```

=== "Solaris"
     ```bash
     pkgadd -d http://get.opencsw.org/now
     /opt/csw/bin/pkgutil -U
     /opt/csw/bin/pkgutil -y -i py_pip 
     /usr/sbin/pkgchk -L CSWpy-pip # list files
     ```

# Listen

Auch (statische!) Listen sind in den verschiedensten Formen möglich, zum Beispiel als ToDo-Liste.

- [x] Lorem ipsum dolor sit amet, consectetur adipiscing elit
- [ ] Vestibulum convallis sit amet nisi a tincidunt
    * [x] In hac habitasse platea dictumst
    * [x] In scelerisque nibh non dolor mollis congue sed et metus
    * [ ] Praesent sed risus massa
- [ ] Aenean pretium efficitur erat, donec pharetra, ligula non scelerisque
