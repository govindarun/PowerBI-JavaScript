# Contributing

## Setup

Clone the repository:
```
git clone https://github.com/Microsoft/PowerBI-JavaScript.git powerbi-client
```

Navigate to the cloned directory

Install local dependencies:
```
npm install
```

## Build:
```
npm run build
```
Or if using VScode: `Ctrl + Shift + B`

## Test
```
npm test
```
By default the tests run using PhantomJS

There are various command line arguments that can be passed to the test command to facilitate debugging:

Run tests with Chrome
```
npm test -- --chrome
```

Enable  debug level logging for karma, and remove code coverage
```
npm test -- --debug
```

Disable single run to remain open for debugging
```
npm test -- --watch
```

These are often combined and typical command for debugging tests is:
```
npm test -- --chrome --debug --watch
```

You can debug by directly calling karma:
```
node node_modules/karma/bin/karma start --browsers=Firefox --single-run=false --watch
```

The build and tests use webpack to compile all the source modules into one bundled module that can execute in the browser.

## Updating the documentation (For those with push permissions only)
First run the command to build the docs and open it to verify the changes are as expected.

```
npm run gulp -- build:docs
```
> There are errors during the TypeDoc compilation step due to some complication with modules however the documentation should still be generated. It's not clear if these are fixable by including more src files in the gulp task or if it's just the nature of TypeDoc lacking capabilities for this project structure.
