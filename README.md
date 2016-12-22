# PatternFly 4 CSS

**PatternFly 4** is the best open source modular design system you'll ever use to build enterprise web applications.

Think of PatternFly as a "skinned" version of [Bootstrap v4](http://v4-alpha.getbootstrap.com/) with additional components and customizations.

This repository is javascript free: you'll only find CSS here.

## Are we there yet?

No, we are not there yet. PatternFly 4 is in its very early stages.

If you as passionate about CSS as we are, you would love to participate in the community and become a contributor.

### Communication channels

You can contact the patternFly community on the [PatternFly mailing list](https://www.redhat.com/mailman/listinfo/patternfly) or chat with us on the [PatternFly slack channel](https://patternfly.slack.com/).


## Contributing to PatternFly 4

PatternFly 4 is implemented using [Pattern Lab Node - Gulp Edition](https://github.com/pattern-lab/patternlab-node).

### Coding style guidelines

Please read the coding style guidelines for PatternFly 4.

The guidelines are a work in progress and a live document, if you have any suggestion please [contact the PatternFly community](#communication-channels) or send a PR.


### Prerequisites

The Pattern Lab Node - Gulp Edition uses [Node](https://nodejs.org) for core processing, [npm](https://www.npmjs.com/) to manage project dependencies, and [gulp.js](http://gulpjs.com/) to run tasks and interface with the core library. Node version 4 or higher suffices.

You can follow the directions for [installing Node](https://nodejs.org/en/download/) on the Node website if you haven't done so already.
Installation of Node will include npm.

### Installing

`npm` is a dependency management and package system which can pull in all of the Gulp Edition's dependencies for you. To accomplish this run the following:

```
npm install
```

Running `npm install` from a directory containing a `package.json` file will download all dependencies defined within.

### Helpful commands

These are some helpful commands you can use on the command line for working with Pattern Lab.

#### List all of the available commands

To list all available commands type:

```
npm run gulp patternlab:help
```

#### Generate Pattern Lab

To generate the front-end for Pattern Lab type:

```
npm run gulp patternlab:build
```

#### Watch for changes and re-generate Pattern Lab

To watch for changes, re-generate the front-end, and serve it via a BrowserSync server,  type:

```
npm run gulp patternlab:serve
```

BrowserSync should open [http://localhost:3000](http://localhost:3000) in your browser.



## Sharing your result on GitHub Pages

Follow this steps to publish your results to [GitHub pages](https://pages.github.com/):


1. Pull master
1. Rebase your branch against master
1. Checkout that branch
1. Run the build
1. Publish the script to github-pages in your repo with the command: `./scripts/publish.sh -r <reponame> public` where `<reponame>` is the local name of your repo (eg. bleathem, origin, etc.)
1. The url is included on the Settings page of your repo under GitHub Pages.

___

Built with :heart: by the [PattrenFly Community](https://www.patternfly.org/community/) and supported by the Red Hat UXD Team.


