---
name: archive
description: Archive the current spec-driven workflow in a named subfolder and prepare for a new one.
disable-model-invocation: true
---

Archive the current workflow without changing the existing root-level `.spec-driven/` workflow contract.

1. Read `.spec-driven/spec.md`. If it does not exist, tell the user there is no completed spec to archive and stop.

2. Derive a concise `kebab-case` archive slug from the spec's `## What to Build` section. Combine it with the current local date as `YYYY-MM-DD-<slug>`. For example, a spec to add CSV export becomes `2026-10-27-add-csv-export`.

3. Show the proposed archive name and ask the user to confirm it or provide a replacement `kebab-case` name. Do not move files until the user confirms.

4. Create `.spec-driven/archive/` if needed. Create the archive directory at `.spec-driven/archive/<archive_name>/`. If that directory already exists, append `-2`, `-3`, and so on until the name is unique.

5. Move every direct child of `.spec-driven/` except `archive/` into the archive directory. Do not modify the files while moving them. Leave `.spec-driven/` containing only `archive/` so it is ready for a new workflow.

6. End the final response with `Done.` and the archive path.