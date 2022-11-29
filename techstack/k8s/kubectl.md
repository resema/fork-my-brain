#gcp #kubernetes #k9s

`kubectl`’s options and flags, such as `label-selector`, `go-templates`, `jsonpath`, etc., can improve query efficiency by filtering and selection.

But `kubectl` provides a method exporting the resource configuration ([YAML](/YAML)) directly into [JSON](/JSON), `-o json`

This can be joined with tools like [jq](/techstack/devops/jq.md)

#### Examples
```bash
# read kind
$ kubectl get pod xxx -n {namespace} -ojson | jq '.kind'

# edit the name
$ kubectl get pod xxx -n {namespace} -ojson | jq '.metadata.name="test"'

```