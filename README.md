[![Ghostery](https://www.ghostery.com/wp-content/themes/ghostery/images/ghostery_logo_black.svg)](https://www.ghostery.com)
---

[![Build Status](https://travis-ci.org/ghostery/ghostery-extension.svg?branch=master)](https://travis-ci.org/ghostery/ghostery-extension) &nbsp; ![GitHub manifest version](https://img.shields.io/github/manifest-json/v/ghostery/ghostery-extension.svg?style=flat-square) &nbsp; [![Chat on Gitter](https://img.shields.io/gitter/room/ghostery/ghostery-expenstion.svg?style=flat-square)](https://gitter.im/ghostery/ghostery-extension) &nbsp; [![Twitter Follow](https://img.shields.io/twitter/follow/ghostery.svg?style=social&maxAge=3600)](https://twitter.com/ghostery)

Ghostery helps you browse smarter by giving you control over ads and tracking technologies to speed up page loads, eliminate clutter, and protect your data. This is the unified code repository for the Ghostery browser extensions in Chrome, Firefox, Opera and Edge.

## Downloads
**Firefox** &ndash; [Download](https://addons.mozilla.org/en-US/firefox/addon/ghostery/) &nbsp; ![amo-rating](https://img.shields.io/amo/rating/ghostery.svg?style=flat-square) &nbsp; ![amo-users](https://img.shields.io/amo/users/ghostery.svg?style=flat-square)

**Chrome** &ndash; [Download](https://chrome.google.com/webstore/detail/ghostery-%E2%80%93-privacy-ad-blo/mlomiejdfkolichcflejclcbmpeaniij) &nbsp; ![Chrome Web Store-rating](https://img.shields.io/chrome-web-store/rating/mlomiejdfkolichcflejclcbmpeaniij.svg?style=flat-square) &nbsp; ![Chrome Web Store-users](https://img.shields.io/chrome-web-store/d/mlomiejdfkolichcflejclcbmpeaniij.svg?style=flat-square&label=users)

**Cliqz** &ndash; [Download](https://s3.amazonaws.com/cdncliqz/update/browser/firefox%40ghostery.com/latest.xpi)

**Opera** &ndash; [Download](https://addons.opera.com/en/extensions/details/ghostery/)

**Edge** &ndash; [Download](https://www.microsoft.com/en-us/store/p/ghostery/9nblggh52ngz)

## Installation
```sh
# Install local npm packages
$ npm install
```

## Building
```sh
# Build all sources
$ npm run build.dev
```

```sh
# Build for production
$ npm run build.prod
```

```sh
# Build and watch for changes
$ npm run build.watch
```

## Enable Debugging / Logging
```javascript
// In manifest.json set
"debug": true,
"log": true,
```

## Testing and Linting
```sh
# Run unit tests
$ npm run test.unit
```

```sh
# Run linter over the ./app and ./src folders
$ npm run lint
```

```sh
# Lint a specific file
$ npm run lint.raw -- src/utils/matcher.js
```

```sh
# Disable lint
$ NO_LINT=true npm run build.dev
# or
$ npm run build.dev -- --env.nolint
```

## Build Docs
```sh
# Build JSDoc files to ./docs
$ npm run docs
```

## Transifex Client
Run Transifex client (tx) in your local synchronized 'develop' branch
Transifex client behavior is determined by .tx/config file in the repo.
```sh
# Install Transifex Client (tx)
$ pip install transifex-client
# Check if install was successful
$ tx --version
```
# Generate your Transifex API token [here] (https://www.transifex.com/user/settings/api/)
# You will use it for initialization of the Transifex client.

# Run initialization command at the root of your repo. 
# It will an interactive session. Example below:
```sh
$ tx init

Welcome to the Transifex Client! Please follow the instructions to
initialize your project.

Creating .tx folder...
Creating config file...
No credentials file was found at /Users/<your user name>/transifexrc. 
Created /Users/<your user name>/.transifexrc
Enter your API token: <your_Tranisfex_API_token>
Verifying token...
Updating /Users/<your user name>/.transifexrc file...
```
# Use Transifex client as follows:
```sh
# Push changes made to _locales/en/messages.json to Transifex
$ tx push -s
# Pull translated files from Transifex to _locales/<lang>/messages.json
$ tx --minimum-perc=100 pull -a 
```
For more information see:
+ [Transifex Client](https://docs.transifex.com/client/introduction)
+ [Transifex Client Workflow](https://docs.transifex.com/integrations/github)
+ [Ghostery Transifex Project](https://www.transifex.com/ghostery-inc/ghostery-8/dashboard/)

## 
## Cliqz Source Code
Ghostery implements the following open-source products from [Cliqz](https://cliqz.com/en/)

[**Human Web**](https://cliqz.com/en/whycliqz/human-web)
+ [How it works](https://cliqz.com/en/magazine/techblog-human-web-reliably-removes-uids)
+ [GitHub](https://github.com/cliqz-oss/browser-core/blob/master/modules/human-web/)

[**Anti-Tracking**](https://cliqz.com/en/whycliqz/anti-tracking)
+ [How it works](https://cliqz.com/en/magazine/how-we-at-cliqz-protect-users-from-web-tracking)
+ [GitHub](https://github.com/cliqz-oss/browser-core/blob/master/modules/antitracking)

[**Ad Blocker**](https://cliqz.com/en/whycliqz/adblocking)
+ [GitHub](https://github.com/cliqz-oss/adblocker)

[**MyOffrz**](https://cliqz.com/en/cliqz-angebote)
+ [GitHub](https://github.com/cliqz-oss/browser-core/blob/master/modules/offers-v2)

### Building Cliqz Modules for Ghostery
Cliqz modules are pre-built and included under the `browser-core` NPM dependency in [package.json](package.json). To reproduce this build process, grab the appropriate Ghostery release (v7.x.x) from the [browser-core](https://github.com/cliqz-oss/browser-core/releases) project.

```sh
$ npm install
$ ./fern.js build configs/ghostery.js --no-maps --environment=production
$ ./fern.js pack configs/ghostery.js
```

## Compatibility

+ Firefox: 52+
+ Firefox Android: 55+
+ Chrome: 49+
+ Opera: 36+
+ Edge: 34.14291+

## Contribute

See [CONTRIBUTING](CONTRIBUTING.md) and [CODE OF CONDUCT](CODE-OF-CONDUCT.md)

## Links
+ [Website](https://ghostery.com/)
+ [Support](https://ghostery.zendesk.com/)
+ [Twitter (@ghostery)](https://twitter.com/ghostery)
+ [Facebook](https://www.facebook.com/ghostery)
+ [Privacy Policy](https://www.ghostery.com/about-ghostery/browser-extension-privacy-policy/)

## Ghostery Team
Ghostery relies on [contributions](https://github.com/ghostery/ghostery-extension/graphs/contributors) from lots of talented people. Our core development team looks like this:

![Christopher Tino](https://avatars3.githubusercontent.com/u/4699516?s=460&v=4) | ![José María Signanini](https://static.cliqz.com/wp-content/uploads/2017/08/jose.jpg) | ![Serge Zarembsky](https://static.cliqz.com/wp-content/uploads/2017/08/serge.jpg) | ![Patrick Lawler](https://static.cliqz.com/wp-content/uploads/2017/08/patrick.jpg) | ![Caleb Richelson](https://avatars0.githubusercontent.com/u/1928870?s=400&v=4) | ![Aziz Aithsaine](https://static.cliqz.com/wp-content/uploads/2017/08/aziz.jpg)
:---:|:---:|:---:|:---:|:---:|:---:
[Christopher Tino](http://github.com/christophertino) | [José María Signanini](https://github.com/jsignanini) | [Serge Zarembsky](https://github.com/zarembsky) | [Patrick Lawler](https://github.com/trickpattyFH20) | [Caleb Richelson](https://github.com/IAmThePan) | Aziz Aithsaine

See the full montage of uncommonly attractive Ghosterians/Cliqzers [here](https://www.cliqz.com/about/team).

## License
[MPL-2.0](https://www.mozilla.org/en-US/MPL/2.0/) Copyright 2018 Ghostery, Inc. All rights reserved.

See [LICENSE](LICENSE)

## Tracker Databases
The [databases](/databases) folder contains JSON skeletons to show the schema expected by the extension pattern [matcher](/src/utils/matcher.js). See the [Database README](/databases/README.md) for more information.
Ghostery's production tracker databases have been purposely excluded from this project, as they remain proprietary to Ghostery, Inc. Which leads us to this grim, yet obligatory...

**Copyright Notice**

The proprietary databases are the intellectual property of Ghostery, Inc. and are protected by copyright and other applicable laws. All rights to them are expressly reserved by Ghostery, Inc. You may not use these databases or any portion thereof for any purpose that is not expressly granted in writing by Ghostery, Inc. All inquires should be sent to [legal@ghostery.com](legal@ghostery.com).  Ghostery, Inc. retains the sole discretion in determining whether or not to grant permission to use the databases. Unauthorized use of the databases, or any portion of them, will cause irreparable harm to Ghostery, Inc. and may result in legal proceedings against you, seeking monetary damages and an injunction against you, including the payment of legal fees and costs.

[![Ghostery](https://www.ghostery.com/wp-content/themes/ghostery/images/github/ghosty_coder.jpg)](https://www.ghostery.com)
