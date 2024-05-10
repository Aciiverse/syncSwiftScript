# scriptWerk -> syncSwiftScript

> A simple Powershell script that copies all changes from one remote to another remote. Variable, fast and very easy to integrate into VS Code Actions! Especially for double repository management.

> [Hier](https://github.com/ScriptWerkstatt/syncSwiftScript/blob/main/README-de.md) gibt es die Doku auch auf deutsch.

## Developer

- [Flowtastisch](https://github.com/flowtastisch)

## Credits

- [PowerShell](https://github.com/PowerShell/PowerShell)

## Features

- Alle Änderungen mit anderem Repository synchronisieren

### Alle Änderungen mit anderem Repository synchronisieren

You can execute the script directly or integrate it into VS code as a task (see instructions below) in order to reflect all changes to a 2nd remote in a matter of seconds without having to change the branch.

Make sure that you also added the 2nd remote (standard remote is always "origin") (see instructions below)

Then you execute the script (either via VS Code Task or directly in PowerShell) and add the source Remote & the target remote. Finished!

HERE GIF PLACE COMMING SOON

## Setup (VS Code Action)

### What you need (VS Code Action)

- [PowerShell](https://github.com/PowerShell/PowerShell) (>= v. 7.4.2.0)

### Step by step guide (VS Code Action)

1. Open your local repository with VS code and open a terminal / cmd there.
2. Then add your new remote with the following command e.g.:

        git remote add <your remote name here> <your remote link hier>

3. Copy the script `syncSwiftScript.ps1` in your repository (e.g. in `./.vscode/syncSwiftScript.ps1`)
4. After you have to add the task for VS code. Go to the `./.vscode/task.json` direction and integrate the following code (simply look at the detailed VS code documentation if you have any questions):

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

5. Now just press `f1` or ` Ctrl + Shift + P` to open the command palette and select `Tasks: Run Task`.
6. Here the new task `sync swift script` should appear. Simply select and proceed as shown in the video:

HERE GIF PLACE COMMING SOON