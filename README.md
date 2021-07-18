# publish-unscoped-package-to-npm-and-github

> Inspired by [Dev.to article](https://dev.to/akinaguda/how-to-publish-an-unscoped-npm-package-to-github-package-registry-19mg) and [this issue](https://github.com/formium/tsdx/issues/854#issuecomment-688474830)

Testing of publishing an unscoped NPM package to Github Package Registry

## Steps

1. Add `publishConfig` section to your **package.json**

```
"publishConfig": {
   "registry": "https://registry-url"
 }
```

2. Modify your **.github/workflows/deploy.yml** file

3. Add `NPM_AUTH_TOKEN` variable in your Repository > Settings > Secrets > New repository secret button. `GITHUB_TOKEN` already exists

## Workflow file

Some notes here how to understand this workflow file:

- [About Github's ENV-vars and EOF](https://docs.github.com/en/actions/reference/workflow-commands-for-github-actions#multiline-strings)
- [About Github Action run command](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idstepsrun)

Now this repository contains the simplest example, you need to manually raise the version for publication
