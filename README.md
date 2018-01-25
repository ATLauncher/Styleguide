# ATLauncher Style Guide
This is the style guide for ATLauncher.

## Contents
This repository is a mono repo powered with Lerna and contains the following packages:

* babel-preset-atlauncher
* eslint-config-atlauncher
* ui-components

## Packages
Each package is a single npm package within the `@atlauncher` scope and is independently published
from one another.

Lerna provides the ability to link the modules up with one another so that packages can be devleoped
with a dependency on another package in this mono repo without the need to publish ahead of time.

### atlauncher-scripts
This package provides all the scripts needed to run, test, lint, build and more for ATLauncher
projects.

Simply include into your project and use the `atlauncher-scripts` command.

This is intended to allow all projects the ability to run commands the same way and evolve how we
do certain things over time by just having it contained within one directory.

* [More Info](https://github.com/ATLauncher/style-guide/blob/master/atlauncher-scripts/README.md)
* [NPM](https://www.npmjs.com/package/@atlauncher/atlauncher-scripts)

### babel-preset-atlauncher
This package contains a preset for Babel which is setup to work for ATLauncher's projects.

It's intended to support all browsers and versions we need to and be a quick preset to get up and
going quickly.

* [More Info](https://github.com/ATLauncher/style-guide/blob/master/babel-present-atlauncher/README.md)
* [NPM](https://www.npmjs.com/package/@atlauncher/babel-present-atlauncher)

### commitlint-config-atlauncher
This package ensures that all commits done to ATLauncher repositories follows our commit standards.

* [More Info](https://github.com/ATLauncher/style-guide/blob/master/commitlint-config-atlauncher/README.md)
* [NPM](https://www.npmjs.com/package/@atlauncher/commitlint-config-atlauncher)

### eslint-config-atlauncher
This package contains our ESLint configs.

This allows all ATLauncher projects to simply extend from this base config to ensure that all code
is consistent and follows the same styling rules.

* [More Info](https://github.com/ATLauncher/style-guide/blob/master/eslint-config-atlauncher/README.md)
* [NPM](https://www.npmjs.com/package/@atlauncher/eslint-config-atlauncher)

### eslint-plugin-atlauncher
This package contains our custom ESLint rules.

Currently only used to allow ignoring method names from requiring `@returns` JSDoc comments.

* [More Info](https://github.com/ATLauncher/style-guide/blob/master/eslint-plugin-atlauncher/README.md)
* [NPM](https://www.npmjs.com/package/@atlauncher/eslint-plugin-atlauncher)

### ui-components
This package contains all the components used by ATLauncher in it's various projects to provide a
consistent visual look through all sites and applications.

It also contains configs to build a React Storybook instance to be able to visually identify and
play with components.

* [More Info](https://github.com/ATLauncher/style-guide/blob/master/ui-components/README.md)
* [NPM](https://www.npmjs.com/package/@atlauncher/ui-components)
* [Storybook](https://atlauncher.github.io/style-guide/)

## Developing
To get developing with any of these modules, first install Lerna globally:

```bash
npm install --global lerna
```

Then go ahead and run a `npm install` in this directory. This will bootstrap all the packages which
will run a npm install and link and cross dependencies.

Then to get up and developing with the modules, simply run `npm run storybook:dev` which will start
a server at `http://127.0.0.1:9001` with the storybook for the `ui-components` package.

To run the linter simply run `npm run lint` which will run the linter on all the packages.

To run tests on all the packages, simply run `npm run test`.

## Publishing
### Production
```bash
npm run publish
```

Or for a single package:
```bash
npm run publish -- --scope @atlauncher/package-name
```

### Testing versions
```bash
npm run publish:prerelease
```

Or for a single package:
```bash
npm run publish:prerelease -- --scope @atlauncher/package-name
```
