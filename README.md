## Changelog

- `0.1` 实现crontab基本功能，实现秒级控制，记录日志和内存占用
- `0.2` 优化和改进，分离配置使可以单独配置文件路径，日志等
- `0.3` 按照PSR重构，支持文件和数据库模式

# Features

- 语法和crontab相同
- 精确到秒级的控制
- 每个任务都使用独立进程
- 支持PSR标准
- 支持文件
- 支持数据库

## About

基于PHP实现的CRONTAB，可以精确到秒级的执行过程，完全兼容Linux系统的crontab写法。

About Crontab... [crontab.org](http://crontab.org/)

## Install

    git clone git://github.com/hfcorriez/php-crontab.git
    cd php-crontab

## Usage

复制配置
____

    cp bin/crontab.ini.example bin/crontab.ini

修改配置
____
bin/crontab.ini:

    [crontab]
    crontab.mode = file

    [file]
    file.path = tasks

    [database]
    database.dsn = "mysql:host=localhost;port=3306;dbname=dbname;charset=UTF-8"
    database.username = username
    database.password = password
    database.table = php_crontab
    database.field = command

    [log]
    log.path = crontab.log
    log.enable = 1


运行例子
____

    cp bin/tasks.example bin/tasks
    ./bin/crontab --master
