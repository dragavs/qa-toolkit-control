# QA Toolkit control

The on/off switch for the **Traction QA Toolkit (QA)** extension. Every installed copy reads [`control.json`](control.json) every 5 minutes and on each Traction page load.

## How to use it

Open `control.json`, click the pencil icon to edit, change a value, then click **Commit changes**.

| To do this | Set |
|---|---|
| **Stop the toolkit for every agent** | `"enabled": false` |
| Turn it back on | `"enabled": true` |
| Show agents a note on the lock screen | `"message": "Paused until Monday"` |
| Make everyone update to a new build | `"minVersion": "1.1.0"` |
| Withdraw one bad version | `"blockedVersions": ["1.0.3"]` |

A change reaches everyone within about 10 minutes, usually sooner.

## Rules

- Keep it valid JSON: double quotes, commas between lines, and no comma after the last line. If the file is broken, the toolkit ignores it and keeps using the last good version.
- Don't delete or rename this file, or make this repository private. If copies can't read the file for 6 hours, they lock.
- This repository has to stay public so the extension can read the file without signing in. There's nothing secret in it.
