# Create Kolmafia Script

Create a kolmafia script with ease, with some additional patches.  If youʼre seeing this package, you probably want [create-kolmafia-script](https://www.npmjs.com/package/create-kolmafia-script) instead.

## Usage
### Note on package managers
There are three major package managers, and several minor package managers, used with Node.js.  The script is mostly tested with Yarn, somewhat tested with NPM and PNPM, and tries to maybe work with Bun and other package managers.

To use this package correctly with Yarn, and maybe with PNPM, you will probably need to use `corepack`, at least until Yarn 6 is released.  With Node 22 or 24, you can enable `corepack` with `corepack enable`.  Note that this is a global setting.


### Upstream
To use the upstream `create-kolmafia-script`, run

```bash
yarn create kolmafia-script <name>
```

### This version

Run
```bash
yarn create @dhouck/kolmafia-script <name>
```

## Note on this repository

This repository is a fork of [loathers/create-kolmafia-script](https://github.com/loathers/create-kolmafia-script).  All branches in this repository track the `main` branch of that repository, directly or indirectly, by rebasing; no branch here has a stable history.

### Releases and packages

The releases and branches include everything in [loathers/create-kolmafia-script](https://github.com/loathers/create-kolmafia-script) at the time of publishing, but are numbered differently.  The patch version will be one higher than upstream, and the prerelease version will be `custom.N`, where `N` is the number of prior release versions.  The first release on this repository was made when upstream was at 0.4.0, so should be `0.4.1-custom.0`.

### Branches
The main branches of this repository are:
* `all-outgoing-prs`: A merge of all PRs that have been submitted to upstream and not yet accepted.
* `danielh/*`: The additional patches I applied that I am not submitting upstream.  Most of these are things Iʼd be happy to submit but expect they donʼt want.
  - `danielh/rspack`: Change the template build system to `rspack`, and make type errors stop the build in all environments
  - `danielh/formatting`: Change some of the default formatting options in the template, like [using](<https://www.reddit.com/r/javascript/s/c6mCGbgTWa> "Reddit page showing this is useful for accessibility") [tabs](<https://lb-stuff.com/tabs> "Block post explaining the rule") [for](<https://dmitryfrank.com/articles/indent_with_tabs_align_with_spaces> "Block post with diagrams demonstrating this working") [indentation](<https://prettier.io/docs/options#tabs:~:text=(Tabs%20will%20be%20used%20for%20indentation%20but%20Prettier%20uses%20spaces%20to%20align%20things%2C%20such%20as%20in%20ternaries.%20This%20behavior%20is%20known%20as%20SmartTabs.)> "Prettier docs saying it uses smart tabs").
  - `danielh/precommit-hooks`: Add precommit hooks using [husky](https://typicode.github.io/husky/) and [lint-staged](https://www.npmjs.com/package/lint-staged) to check the code style and linting, and to build and test.
* `danielh-release`: Built on top of `all-outgoing-prs`, with the additional changes from the `danielh/*` branches.  This branch is used for releases to GitHub Packages.

The primary purpose of the published `all-outgoing-prs` branch is integration testing of my various PRs.  The primary purpose of the `danielh-release` branch is to publish `@dhouck/create-kolmafia-script` to GitHub Packages.
