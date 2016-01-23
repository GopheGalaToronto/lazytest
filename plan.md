## Iteration plan

### v.0

- Basic file watcher
- Test re-runner


### MVP

- Non-stdlib package dependency tree for tests and watched files
- Test runner capable running a subset of tests based on the packages affected by notification
- Pretty display test results, show failed tests + summary last

### v. +1

- Function/var/const  etc granularity instead of package (leverage go coverage tool?)
- logging

### v. +2

- Display tests running diffs instead of full output
- Basic webinterface with diffs pushed over socket


## Code/libraries/projectsto re-use:
1. Watcher https://github.com/c2h5oh/fresh/blob/master/runner/watcher.go

2. Dependencies (let's find code in go tools that does it)
    - all package deps `go list -f {{.Deps}}`
    - all package deps that are non in stdlib `go list -f '{{.Deps}}' | tr "[" " " | tr "]" " " | xargs go list -f '{{if not .Standard}}{{.ImportPath}}{{end}}'`
    - go cover?

3. Test runner:
    - https://github.com/stretchr/testify/blob/master/suite/suite.go#L59
    - https://golang.org/pkg/testing/
    - https://github.com/remogatto/prettytest  (implements all of v.0 http://goconvey.co

4. Web interface
    - http://goconvey.co
