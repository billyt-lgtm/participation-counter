## Cursor Cloud specific instructions

This repo is a single static page, `index.html` (Crit Topics 2026). There is no package manager, lockfile, linter, or test suite, so there is nothing to install before a session.

Serve it from the repo root with `python3 -m http.server 8000` and open `http://127.0.0.1:8000/`. Opening the file with `file://` does not reliably load the Supabase client from jsDelivr.

Counts live in the hosted Supabase project hardcoded in `index.html` (table `participation`, row id `team`, column `counts`). There is no local database. `fetchCounts` ignores request errors, substitutes `{}`, and still sets the status to "Live", so a dead backend looks like every person is at 0. On 2026-10-30, `ebjfgetbzfyiudqdysmo.supabase.co` was NXDOMAIN on public DNS; plus and minus still change the on-screen number, and Refresh loads the empty fallback so the change does not stick. Once that host resolves again, avoid **Reset All** unless the shared row should be zeroed for every name.
