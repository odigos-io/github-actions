# github-actions
odigos github actions to use in various repos CI

## Available Actions

### slack-release-notification

A reusable action that sends Slack notifications based on job status for release updates. Automatically detects success/failure states and sends appropriate messages to your Slack channel.

**Usage:**
```yaml
- name: Notify Slack Release Status
  uses: odigos-io/github-actions/.github/actions/slack-release-notification@main
  with:
    webhook-url: ${{ secrets.SLACK_WEBHOOK_URL }}
    success-description: "Odigos collector linux packages released successfully"
    failure-description: "ERROR: failed to publish odigos collector linux packages"
    tag: ${{ steps.extract_tag.outputs.tag }}
```

For detailed documentation, see [slack-release-notification README](.github/actions/slack-release-notification/README.md).
