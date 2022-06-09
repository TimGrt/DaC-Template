# Spezielle Elemente in MkDocs-Material

Das Material-Theme ist eines der beliebtesten Themes für MkDocs und bringt einige Erweiterungen für die visuell ansprechene Gestaltung eurer Dokumentation mit. 
Eine vollständige Übersicht inklusive Codebeispielen findet sich [hier](https://squidfunk.github.io/mkdocs-material/reference/), einige Highlights haben wir auf dieser Seite eingebaut.

## Admonitions

Admonitions, auch _Call-Outs_ genannt, sind eine gute Wahl um zusätzliche Inhalte einzufügen, ohne den Dokumentfluss wesentlich zu unterbrechen. MkDocs bietet mehrere verschiedene Arten von Admonitions und ermöglicht Verschachtelung beliebiger Inhalte.

???+ success annotate "Admonition"

      Es gibt eine große Anzahl (1) [Typen von Admonitions](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#supported-types), die alle häufigen Nutzungszwecke abdecken - zum Beipiel `alert`, `warning`, `info` und `success`.(2)

1:    :man_raising_hand: Die [MKDocs Material-Dokumentation](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#supported-types) ist sehr gut geschrieben und enthält viele Beispiele für Admonitions
2:    Diese Anmerkungen lassen sich ebenfalls sehr leicht in Markdown schreiben und integrieren.

## Codeblöcke

Auch Codeblöcke lassen sich sehr einfach einfügen und werden automatisch mit einem _Kopieren_-Button versehen. Sie werden über drei *Backticks* eingefasst.  
Wenn zu Beginn des Codeblocks die entsprechende Codesprache angegeben wird ergänzt MkDocs farbliche passende Syntax-Highlights.

Hier beispielsweise im YAML-Format:

````
```yaml
site_name: CC Documentation as Code Template
copyright: Copyright &copy; Computacenter 2022
```
````

Dieser Code-Block wird folgendermaßen dargestellt:

```yaml
site_name: CC Documentation as Code Template
copyright: Copyright &copy; Computacenter 2022
```

Einzelne Zeilen in Code-Blöcken können folgendermaßen hervorgehoben werden, Zeilen können nummeriert werden:

````
```py hl_lines="2 3" linenums="1"
def sort_ip(unsorted_ip_list):
    """ Sort list of IP addresses """
    
    if not isinstance(unsorted_ip_list, list):
        raise AnsibleFilterTypeError("Filter needs list input, got '%s'" % type(unsorted_ip_list))
    else:
        sorted_ip_list = sorted(unsorted_ip_list, key=netaddr.IPAddress)
        
    return sorted_ip_list
```
````

In MkDocs wird der Block entsprechend dargestellt:

```py hl_lines="4 5" linenums="1"
def sort_ip(unsorted_ip_list):
    """ Sort list of IP addresses """
    
    if not isinstance(unsorted_ip_list, list):
        raise AnsibleFilterTypeError("Filter needs list input, got '%s'" % type(unsorted_ip_list))
    else:
        sorted_ip_list = sorted(unsorted_ip_list, key=netaddr.IPAddress)
        
    return sorted_ip_list
```

## Tabs

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

## Listen

Auch (statische!) Listen sind in den verschiedensten Formen möglich, zum Beispiel als ToDo-Liste.

- [x] Lorem ipsum dolor sit amet, consectetur adipiscing elit
- [ ] Vestibulum convallis sit amet nisi a tincidunt
    * [x] In hac habitasse platea dictumst
    * [x] In scelerisque nibh non dolor mollis congue sed et metus
    * [ ] Praesent sed risus massa
- [ ] Aenean pretium efficitur erat, donec pharetra, ligula non scelerisque

## Tabellen

Alle Tabellen können in MkDocs selbstständig sortiert werden, in der Titelzeile kann durch einen Klick alphabetisch aufsteigend oder absteigend sortiert werden.

| Method      | Description                          |
| ----------- | ------------------------------------ |
| `GET`       | :material-check:     Fetch resource  |
| `PUT`       | :material-check-all: Update resource |
| `DELETE`    | :material-close:     Delete resource |

Die Tabelle wird in Markdown folgendermaßen definiert. Hier werden zusätzlich noch Symbole in der zweiten Spalte verwendet, diese werden durch zwei Doppelpunkte eingefasst:

```markdown
| Method      | Description                          |
| ----------- | ------------------------------------ |
| `GET`       | :material-check:     Fetch resource  |
| `PUT`       | :material-check-all: Update resource |
| `DELETE`    | :material-close:     Delete resource |
```