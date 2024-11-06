# Check workflow type action

This is a helpful action to check the type of workflow that is running. It can be used to check if the workflow is a
pull request, push, or any other type of workflow.

The result is that the action will output the type of workflow that is running which can be used to conditionally run
steps in the workflow.

## Usage

```yaml
- name: Check workflow type
  uses: quouch/check-workflow-type-action@v1
  id: check-workflow-type
```

## Testing with [act](https://nektosact.com)

You can test this action with [act](https://nektosact.com). Some example events are provided in the `examples` directory.

### Push to main event
```bash
act push -e examples/push-to-main.json
```

### Pull request event
```bash
act pull_request -e examples/pull-request.json
```
