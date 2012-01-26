# Monit Graph

## Introduction

Monit Graph is a logging and graphing tool for Monit written in
PHP5. It can manage big amounts of data, and will keep a history of
Monit statuses.

This is a **fork** of the google code [project](https://code.google.com/p/monit-graph/).

## Features

 * Easy to manage and customize.

 * Several different graphs (Google Charts) of memory, cpu, swap and alert activity.

 * Data logging with XML files.

 * Chunk rotation and size limitation.

 * Multiple server setup.

## HOWTO

 1. Get [monit](http://mmonit.com/monit) and
    [enable](http://mmonit.com/monit/documentation/monit.html#monit_httpd)
    the buitin HTTP server.

 1. Set the permissions for `data` directory to 775.
 
 2. Change permissions for `data/index.php` to 644.

 3. Modify `config.php` to match your monit setup and configure the
    graphing.  Set this file readable only by the owner and the PHP
    process owner (`www-data` on Debian), i.e., permission '0440'.
    
 4. Setup a crontab job to run cron.php every minute. 
 
    Example:
    
        * * * * * php /path/to/monit-graph/cron.php >> /tmp/monit-graph.log
    
 5. Verify after a few minutes of running that the logging
    happens. You can check the php error log if there seams to be
    something wrong.

 6. Protect access to `index.php` using basic authentication.
 
 7. Disable access to the `tools` directory.

## Author

This script was originally created by Dan Schultzer from
[Dream Conception](http://dreamconception.com/) and
[Abcel](http://abcel-online.com).

## TODO

Convert this to Lua and make use of Nginx
[embedded Lua](http://wiki.nginx.org/HttpLuaModule) module.
