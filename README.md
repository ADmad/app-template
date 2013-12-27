# App Template

An empty CakePHP project for use with composer

## Installation

	composer -sdev create-project friendsofcake/app-template ProjectName

This will create a new project, with dependencies, based on this repository. Be sure to point
the webserver at the `app/webroot` folder (a [production install][1]), ensure that [url rewriting][2]
is configured correctly.

## Non-default Configuration

By default, the following has been enabled:

- Composer Autoloading
- Setting Timezone to UTC
- Setting database connection encoding to utf8 in `database.php.defaut`

You may change either of these at your leisure.

## Heroku Compatibility

This application template is compatible with the [CHH/heroku-buildpack-php](https://github.com/CHH/heroku-buildpack-php) project. To use, simply configure your buildpack:

    heroku config:set BUILDPACK_URL=https://github.com/CHH/heroku-buildpack-php
    heroku config:set LOG_PATH=/app/vendor/php/var/log/
    heroku config:set SECURITY_SALT=SOME_ALPHANUMERIC_SALT_HERE
    heroku config:set SECURITY_CIPHER_SEED=SOME_NUMERIC_SEED_HERE

## Note about dependencies

FriendsOfCake encourages the use of composer and it's best not to mix composer with git submodules for
dependency management. If you need to use submodules you might notice `/vendor` and `/Plugin` folders are
ignored by git. Composer creates those directories when installing vendors and plugins.

There a few ways to solve this:
- edit the `.gitignore` file
- use the `-f` param with `git add Plugin/SomePlugin -f`
- use `app/Plugin` and `app/Vendor` for your submodules.

 [1]: http://book.cakephp.org/2.0/en/installation.html#production
 [2]: http://book.cakephp.org/2.0/en/installation/url-rewriting.html
