# wp-advanced-logs
A really simple Wordpress plugin to improve WP logging capabilities for developpers, based upon the [log4php](https://logging.apache.org/log4php/index.html) framework. 

Wordpress default log system (wp-content/debug.log) isn't very powerful. If you have to trace events with accuracy, this plugin tries to help developpers by adding useful PHP methods to add important informations in a log file

## Features

* Add and instantiate a Logger Class you can access everywhere in your Code (Theme, plugin)
* Provide several methods to trace your data in log files
* Support various built-in log message formats, including XML, HTML or user-defined pattern

## Installation

The plugin can be installed directly into your plugins folder "as-is".

## Quick start

The plugin comes with a default 'basic' logger and is ready to use after you activate in in the Wordpress extension dashboard.

To call the default logger in your code, simply add this line of code:
```php
$logger = Logger::getLogger('default');
```
Here are few examples of what you can do with this logger:
```php
...
$logger.debug('Here is a really useful debug log');
try {
  ...
  $logger.info('Coolest logging plugin for Wordpress is here!');
  // The following code throws an exception
  generateException();
  ...
} catch( exception e ) {
  $logger.error('Oups, Looks like something went wrong :(');
  ...
}
```

The corresponding log file will be created in the `/wp-content/uploads/wp-advanced-logs` folder and will look like this:
```
2016-02-27T19:42:16+01:00 myClass.php DEBUG Here is a really useful debug log
2016-02-27T19:42:17+01:00 myClass.php INFO Coolest logging plugin for Wordpress is here!
2016-02-27T19:42:17+01:00 myClass.php ERROR Oups, Looks like something went wrong :(
```

The default logger level is set to DEBUG but it will be possible to override it in a future release.

## Settings

Here are some of the settings you'll be able to change in a near future:
* Customize Log file name and destination
* Choose between various appenders types
* Configure the default log level (Trace > Debug > Info > Warn > Error > Fatal)

## License

The WordPress Plugin Boilerplate is licensed under the [GPL v3](http://www.gnu.org/licenses/gpl.html)

# Credits

The WordPress Advanced logs plugin was started in 2016 by [Julien Le Thuaut](http://jltweb.info/). If you're interested in contributing or suggesting additional features, please let me know [Julien Le Thuaut](http://jltweb.info/contact/)
