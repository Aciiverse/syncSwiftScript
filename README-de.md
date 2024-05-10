# scriptWerk -> syncSwiftScript

> Ein einfaches Powershell-Skript, das alle Änderungen von einem Remote auf ein anderes kopiert. Einfach, schnell und sehr einfach in VS Code Actions integrierbar! Speziell für die doppelte Repository-Verwaltung.

> [Here](https://github.com/ScriptWerkstatt/syncSwiftScript/blob/main/README.md) is the doc also in english.

## Entwickler*Innen

- [Flowtastisch](https://github.com/flowtastisch)

## Credits

- [PowerShell](https://github.com/PowerShell/PowerShell)

## Features

- Alle Änderungen mit anderem Repository synchronisieren

### Alle Änderungen mit anderem Repository synchronisieren

Du kannst das Script direkt ausführen oder in VS Code als eine Task einbinden (siehe Anleitung unten) um somit in Sekundenschnelle alle Änderungen auch auf ein 2. Remote zu spiegeln, ohne den Branch wechseln zu müssen.

Vergewissere, dass du vorher den 2. Remote auch hinzugefügt hast (Standard remote ist immer "origin") (siehe Anleitung unten)

Danach fürst du das Script aus (entweder per VS Code Task oder direkt in PowerShell) und gibst den Source Remote & den Target Remote an. Fertig!

![syncSwiftScript 400 Preview T](https://github.com/ScriptWerkstatt/syncSwiftScript/assets/107034726/067dc0db-5a44-40f9-b122-4259357e457a)

## Setup (VS Code Action)

### Was du brauchst (VS Code Action)

- [PowerShell](https://github.com/PowerShell/PowerShell) (>= v. 7.4.2.0)

### Schritt für Schritt Anleitung (VS Code Action)

1. Öffne dein lokales Repository mit VS Code und öffne dort ein Terminal / cmd.
2. Dann füge dein neues Remote hinzu zB. mit dem folgendem Befehl:

        git remote add <Dein Remote Name Hier> <Dein Remote Link Hier>

3. Kopiere das Script `syncSwiftScript.ps1` in dein Repository (zB. in `./.vscode/syncSwiftScript.ps1`)
4. Nachdem musst du die Task für VS-Code hinzufügen. Gehe dazu in die `./.vscode/task.json` und binde folgenden code ein (Bei Fragen einfach die ausführliche VS Code Dokumentation angucken):

        {
            "tasks": [
                {
                    "label": "sync swift script",
                    "type": "shell",
                    "command": "./.vscode/syncSwiftScript.ps1",
                    "problemMatcher": []
                }
            ]
        }

5. Jetzt einfach `F1` oder `Strg + Shift + P` drücken um die Befehlspalette zu öffnen und `Tasks: Run Task` auswählen.
6. Hier sollte die neue Task `sync swift script` dann auftauchen. Einfach auswählen und wie im Video gezeigt vorgehen:

![syncSwiftScript 400 Preview T](https://github.com/ScriptWerkstatt/syncSwiftScript/assets/107034726/067dc0db-5a44-40f9-b122-4259357e457a)
