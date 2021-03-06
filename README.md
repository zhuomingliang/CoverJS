CoverJS (alpha)
===============

Make sure all your code is tested, don't miss anything.
CoverJS intruments your code. Using the instrumented code with your tests
will result in a nice object, which can be passed through one of the reporters
to create a nice graphical output of your code.

Instead of instrumenting lines (like JSCoverage), CoverJS will instrument
statements, which should result in a more precise result.

### Dependencies

- [Esprima](https://github.com/ariya/esprima) a wonderful JavaScript parser
- [Escodegen](https://github.com/Constellation/escodegen)
- [Prime](https://github.com/mootools/prime) awesome little OOP library

### Reporters

 - HTML
 - Text

### CLI Usage

To instrument the code, CoverJS comes with a CLI tool:

	coverjs --output cov/ file.js test/*

### Reporting

The instrumented code should be executed to count the number of calls for each statement.
Usually your tests will try to cover each statement.

An example code that will capture the output and generate a HTML report would look like:

```js

var HTMLReporter = require('../lib/reporters/HTMLReporter');

require('../test-cov/test/fixture.js');

var reporter = new HTMLReporter(global.__$coverObject);
console.log(reporter.report());
```

The output stream can be redirected to a file using

	node test.js > report.html

so the result can be viewed in a browser

#### Screenshot

![Screenshot](http://i.imgur.com/lxGpb.png)
