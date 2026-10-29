# Working rules for Claude on this repo

## Token efficiency comes first (owner's standing instruction)
The owner wants every session to use as few tokens as possible. Always:

- **Never read `index.html` or `test-site/index.html` whole.** Each is ~700–800 KB (~180k tokens).
  Find the spot with `grep -n` and read only the lines you need (`sed -n 'A,Bp'`, or Read with offset/limit).
- **Never print line 416 of `index.html`** (the Arabic dictionary, `/*AR_DICT*/ … /*END_AR_DICT*/`, ~426 KB)
  or the base64 logo lines (7, 249). To add translations, append keys with a small Python script.
- **Edit with targeted replacements** (Edit tool, `sed`, or a short Python script). Never rewrite the whole file.
- **Batch changes**: make all requested edits, then republish the artifact and push once.
- **No exploration beyond the task**: don't re-read README/docs unless needed; don't list the database unless the task needs data.
- **Keep replies short**: what changed, and the link. No step recaps.
- **Verify cheaply**: a headless browser check of the one section changed, not a full tour with many screenshots.

## Scope: this repository is ONLY the Al Risaleh grants platform (owner's standing instruction)
- Work here only on the Al Risaleh Foundation grants & supplies platform (artifact `431d9199-…`, `test-site/`, the "Daily grant finder update" task).
- **Never** bring in, mention, document or change the owner's other product (Kinora / Recovery Intelligence, repo `recovery-intelligence`) from a session about this project. If a request seems to be about Kinora (patients, wounds, X-rays/DICOM, rehab, WhatsApp check-ins), stop and ask which project it is for.
- Keep commands, files, commits and scheduled tasks for the two projects completely separate.

## Project facts (so you don't need to rediscover them)
- Artifact slug: `431d9199-d1e2-431d-b6a8-57e3a83f8c50` (publish `index.html` with publish_files).
- `test-site/` is the standalone Netlify version (no artifact runtime).
- Daily scheduled task "Daily grant finder update" edits only the `opps` collection; its rules are in `docs/daily-update-task.md`.
