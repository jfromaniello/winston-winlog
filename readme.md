
# WinLog

  Windows Event Log logger for node.js [Winston](https://github.com/flatiron/winston) module.

## Installation

    $ npm install winlog
    $ npm install winston


## Usage

Configure :

```js
  var winston = require('winston'),
      winlog = require("winlog");

  winston.add(winlog.EventLog, { appName: 'myapp' });
  winston.setLevels(winlog.config.levels);
```

Then you can do:

```bash
  winston.info("this is an info message");
  winston.warning("this is an warning message");
  winston.error("this is an error message");
```

And you will see

![2012-04-07_1148.png](http://joseoncodecom.ipage.com/wp-content/uploads/images/2012-04-07_1148.png)

## How it works

This transport call [eventcreate.exe](http://technet.microsoft.com/en-us/library/bb490899.aspx) with [child_process.exec](http://nodejs.org/docs/v0.6.7/api/child_processes.html#child_process.exec). 

In order to execute eventcreate.exe you need to run the application under an elevated prompt: ie administrator or system account. Windows services run with the system account so this project goes well with [WinSer](https://github.com/jfromaniello/winser).

The transport will do nothing if you run it on a different platform than win32.

## License 

(The MIT License)

Copyright (c) 2012 Jose Romaniello &lt;jfromaniello@gmail.com&gt;

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.