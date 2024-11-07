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
- name: Build action
  if: steps.check-workflow-type.outputs.doBuild
  run: echo "This is a push workflow"
```

## Outputs
Defines the variables that will be available to other steps in the workflow.  
- isPR: Indicates if the event is a pull request.
- isDraft: Indicates if the pull request is a draft.
- isPush: Indicates if the event is a push.
- isMainBranch: Indicates if the push is to the main branch.
- doBuild: Indicates if the project should be built.
- doRelease: Indicates if the project should be released.
- checkRelease: Indicates if the release should be checked but not released.

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
