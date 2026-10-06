# Automatic Last Modified Metadata
This GitHub Action automatically updates the latest modification information in Markdown (`.md`) files within the repository.

## Purpose

The **Update Last Modified** workflow automatically records the date, time, and display name of the person who last modified a Markdown document.

## Workflow

| Property | Value |
|-----------|-----------|
| File location | `.github/workflows/update-last-modified.yml` |
| Workflow name | `Update Last Modified Details` |

The workflow is triggered automatically when a Markdown file is modified and pushed to the repository. Only modified Markdown files containing the required markers are updated.

## Required Configuration in Markdown Files

Each Markdown file must contain the following block under the **Last Modified** section:

```md
#### Last Modified

<!-- LAST_MODIFIED_START -->
06-10-2026 13:54:25 by Skenderbyte
<!-- LAST_MODIFIED_END -->
```

### Important Requirements

- The `LAST_MODIFIED_START` marker is required.
- The `LAST_MODIFIED_END` marker is required.
- Everything between the markers is automatically replaced by the workflow.
- The marker block must be present for automatic updates to work.
- The heading `#### Last Modified` is recommended for consistency.

## How It Works

1. A user modifies a Markdown file.
2. The change is committed and pushed to GitHub.
3. The **Update Last Modified** workflow is triggered.
4. The workflow identifies the modified Markdown file and updates the date, time, and display name.
5. The workflow automatically commits the updated metadata back to the repository.

## Example Result

```md
#### Last Modified

<!-- LAST_MODIFIED_START -->
06-10-2026 13:54:25 by Skenderbyte
<!-- LAST_MODIFIED_END -->
```

## Notes

- Markdown files without the required markers are not updated.
- Only Markdown files modified in the most recent commit are processed.
- Workflow-generated commits are excluded from triggering the workflow again, preventing an infinite update loop.
- GitHub usernames can be mapped to display names for improved readability in documentation.



#### Last Modified
<!-- LAST_MODIFIED_START -->
06-10-2026 13:54:25 by Skenderbyte
<!-- LAST_MODIFIED_END -->
