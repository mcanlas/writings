---
updated: Dec 2022
---
# Testing GitHub Actions workflows

- Workflows in GitHub Actions support being triggered manually
  - If they are figured to listen to this trigger (known as a `workflow_dispatch` event)
  - And if they have been triggered by GHA **at least once**
    - Even if the workflow originates from a branch, this does not matter
- To easily test brand new, workflows in branches, even if you intend for them to only be manually triggered, you should bootstrap them:
  - Temporarily add `push` with no conditions onto your workflow (ideally with no-op jobs)
  - This will cause the GHA to see your workflow for the first time
  - After being seen at least once, you can remove the `push` trigger and use manual triggers from the UI
