PHP Parallel Lint
=================

This tool check syntax of PHP files faster then serial check with fancier output.

Running parallel jobs in PHP inspired by Nette framework tests.

![Alt text](/tests/examples/example-images/use-success.png?raw=true "Example use of tool")

Install
-------

Just create a `composer.json` file and run the `php composer.phar install` command to install it:

```json
{
    "require-dev": {
        "jakub-onderka/php-parallel-lint": "0.*"
    }
}
```

For colored output install suggested package `jakub-onderka/php-console-highlighter`. After a `composer.json` file include:

```json
{
    "require-dev": {
        "jakub-onderka/php-parallel-lint": "0.*",
        "jakub-onderka/php-console-highlighter": "0.*"
    }
}
```

PHP Parallel Lint require PHP version 5.4 and newer, for support with PHP version 5.3 please use 0.7.1 version instead.

Example output
--------------

![Alt text](/tests/examples/example-images/use-error.png?raw=true "Example use of tool with error")

Recommended setting for usage with Symfony framework
--------------

For run from command line:

```
$ ./bin/parallel-lint --exclude app --exclude vendor .
```

or setting for ANT:

```xml
<condition property="parallel-lint" value="${basedir}/bin/parallel-lint.bat" else="${basedir}/bin/parallel-lint">
    <os family="windows"/>
</condition>

<target name="parallel-lint" description="Run PHP parallel lint">
    <exec executable="${parallel-lint}" failonerror="true">
        <arg line='--exclude ${basedir}/app/' />
        <arg line='--exclude ${basedir}/vendor/' />
        <arg line='${basedir}' />
    </exec>
</target>
```

------

[![Build Status](https://travis-ci.org/JakubOnderka/PHP-Parallel-Lint.svg?branch=master)](https://travis-ci.org/JakubOnderka/PHP-Parallel-Lint)
