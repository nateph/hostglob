[![CircleCI](https://circleci.com/gh/circleci/circleci-docs.svg?style=shield)](https://circleci.com/gh/nateph/hostglob) ![GitHub](https://img.shields.io/github/license/nateph/hostglob)
### Hostglob

This library contains tools for collapsing and uncollapsing host globs.

Examples:
```
hosts := "hostprefix[001:004].hostsuffix.com"

if hostglob.IsGlob(hosts) {
    uncollapsed, err := hostglob.Uncollapse(hosts)
    if err != nil {
        ...
    }
}
```
In the above example, `uncollapsed` would give us the slice:
```
[hostprefix001.hostsuffix.com hostprefix002.hostsuffix.com hostprefix003.hostsuffix.com hostprefix004.hostsuffix.com]
```

Currently, hostblob supports 1, 2, 3 or 4 digits in the hostname range.
