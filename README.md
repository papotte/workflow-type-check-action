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
