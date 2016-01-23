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
