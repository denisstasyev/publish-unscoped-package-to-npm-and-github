# publish-unscoped-package-to-npm-and-github

> Inspired by [Dev.to article](https://dev.to/akinaguda/how-to-publish-an-unscoped-npm-package-to-github-package-registry-19mg) and [this issue](https://github.com/formium/tsdx/issues/854#issuecomment-688474830)

Testing of publishing an unscoped NPM package to Github Package Registry

NPM:

[![NPM version](https://img.shields.io/npm/v/publish-unscoped-package-to-npm-and-github?style=flat)](https://www.npmjs.com/package/publish-unscoped-package-to-npm-and-github)
[![NPM downloads](https://img.shields.io/npm/dt/publish-unscoped-package-to-npm-and-github?style=flat)](https://www.npmjs.com/package/publish-unscoped-package-to-npm-and-github)

GPR (GitHub Package Registry):

[![GPR version](https://img.shields.io/github/package-json/v/denisstasyev/publish-unscoped-package-to-npm-and-github?style=flat)](https://github.com/denisstasyev/publish-unscoped-package-to-npm-and-github/packages)
[![GPR downloads](https://img.shields.io/github/downloads/denisstasyev/publish-unscoped-package-to-npm-and-github/total?style=flat)](https://github.com/denisstasyev/publish-unscoped-package-to-npm-and-github/packages)

## Steps

1. Add `publishConfig` section to your **package.json**

```
"publishConfig": {
   "registry": "https://registry-url"
 }
```

2. Modify your **.github/workflows/deploy.yml** file

3. Add `NPM_AUTH_TOKEN` variable in your Repository > Settings > Secrets > New repository secret button. `GITHUB_TOKEN` already exists

4. Success :tada:

## Usage

_From NPM:_

`npm install publish-unscoped-package-to-npm-and-github`

_From GPR:_

`npm install @denisstasyev/publish-unscoped-package-to-npm-and-github`

Possibly you will need **.npmrc** file:

```
@denisstasyev:registry = https://npm.pkg.github.com
```

Find out the registry used: `npm config get registry`

Show complete package manager configuration: `npm config ls -l`

## Workflow file

Some notes here how to understand this workflow file:

- [About Github's ENV-vars and EOF](https://docs.github.com/en/actions/reference/workflow-commands-for-github-actions#multiline-strings)
- [About Github Action run command](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idstepsrun)

Now this repository contains the simplest example, you need to manually raise the version for publication. For automatic version control you can use some tools like [semantic-release](https://github.com/semantic-release/semantic-release) ([example of usage in Github Action](https://github.com/denisstasyev/rollup-plugin-inline-code/blob/main/.github/workflows/publication.yml#L30) and [necessary **.releaserc.json** file](https://github.com/denisstasyev/rollup-plugin-inline-code/blob/main/.releaserc.json))
