# Slack Release Notification Action

This action sends Slack notifications based on job status for release updates. It automatically detects success/failure states and sends appropriate messages to your Slack channel with visual indicators (✅ for success, ❌ for failure).

## Usage

```yaml
- name: Notify Slack Release Status
  uses: your-org/github-actions/.github/actions/slack-release-notification@main
  with:
    webhook-url: ${{ secrets.SLACK_WEBHOOK_URL }}
    success-description: "Odigos collector linux packages released successfully"
    failure-description: "ERROR: failed to publish odigos collector linux packages"
    tag: ${{ steps.extract_tag.outputs.tag }}
```

## Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `webhook-url` | Slack webhook URL | Yes | - |
| `success-description` | Description message for successful releases | Yes | "Release completed successfully" |
| `failure-description` | Description message for failed releases | Yes | "Release failed" |
| `tag` | Release tag | No | - |

## Slack Message Format

### Success Message
```json
{
  "description": "Your success message",
  "tag": "v1.0.0"
}
```

### Failure Message
```json
{
  "link": "https://github.com/owner/repo/actions/runs/123456789",
  "description": "Your failure message",
  "tag": "v1.0.0"
}
```
