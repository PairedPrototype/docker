# Docker

A place to keep all my docker files for various projects

## Projects/images

### Circle-Ci

Based off the `circleci/node:12.8.1` image.
Adds dependencies needed to run puppeteer.
Puppeteer is **not** included and should be added as a dev dependency to the
`project.json` using this command `npm i -D puppeteer`, then you must require
puppeteer in the test framework's config like this karma example snippet:

```js
process.env.CHROME_BIN = require("puppeteer").executablePath();

module.exports = function(config) {
    config.set({
        browsers: ["headlessChrome"],
        customLaunchers: {
            headlessChrome: {
                base: "ChromeHeadless",
                flags: ["--no-sandbox"],
            },
        },
    });
};
```
