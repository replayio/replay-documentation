# How programmatic recordings work (1)

Replay currently maintains three runtimes ([Firefox](https://github.com/replayio/gecko-dev), [Chromium](https://github.com/replayio/chromium), and [Node](https://github.com/replayio/node)). Firefox supports Mac, Linux, and Windows (Alpha). Node is currently in beta for Mac and Linux. Chromium is currently in beta for Linux.

Replay can also integrate [Playwright](https://playwright.dev) and [Puppeteer](https://pptr.dev) by configuring each to use the appropriate binary. See our docs on [Recording Playwright](https://www.notion.so/Recording-Playwright-Beta-b62474b5aadd49e2b0c44a7580b0617e?pvs=21) and [Recording Puppeteer](https://www.notion.so/Recording-Puppeteer-Experimental-5525cfad405e41a18b940af3d09d68be?pvs=21) for more details. Replay also has alpha support for recording [Cypress](https://cypress.io) tests via [@replayio/cypress](https://www.npmjs.com/package/@replayio/cypress).

## Versions and rebasing

Rebasing our runtimes is less a question of merge conflicts and more a question of new non-determinism. This is because the diffs of our runtimes are fairly small (~3k lines of code) and each time we rebase the runtimes have changed quite a bit. We try staying in sync with the browser releases.

Staying up-to-date with Playwright and Puppeteer in theory is fairly straightforward. We do not change their APIs and they do not introduce that much new nondeterminism. Going forward, we plan on adding automation so that we can stay up-to-date here as well.