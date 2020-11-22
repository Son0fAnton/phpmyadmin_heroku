phpmyadmin_heroku
=================

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

This is my kludgy way of running phpMyAdmin on Heroku. All you need to do is
customize `config.inc.php` as you would normally to get things running.
Note: The `config.inc.php` is the sample file provided with phpMyAdmin.

If you wish to another display site on the root url and phpmyadmin at
[url]/phpmyadmin, change the `procfile` to the following:
`web: vendor/bin/heroku-php-apache2 /`.

Please register an issue or submit a PR if you think there's a better way of
doing this!

To see this in action, go to https://phpmyadmin-heroku.herokuapp.com which is
built from the `sample_cleardb` branch. That `config.inc.php` has been
configured to bypass login and give complete access. Please be friendly.

### Config vars

<dl>
  <dt>PHPMYADMIN_BLOWFISH_SECRET</dt>
  <dd>This is needed for cookie based authentication to encrypt password in cookie</dd>
  <dt>MYSQL_HOST</dt>
  <dd>The hostname or IP address of your MySQL-server, optional</dd>
  <dt>ALLOWARBITRARYSERVER</dt>
  <dd>If enable this, allows you to log in to arbitrary servers using cookie authentication</dd>
  <dt>WHITELIST_IP</dt>
  <dd>
    Allowed IP address, optional<br />
    You can use this parameter to restrict access to your phpMyAdmin app.
  </dd>
</dl>

### Create Deploy to Heroku button

For example, you might have the following button URL:
```html
<a href="https://heroku.com/deploy?template=https://github.com/velizarn/phpmyadmin_heroku/tree/master&
env[WHITELIST_IP]=11.11.11.11">Deploy to Heroku</a>
```
This will cause the Heroku app-set interface to prefill IP address for the WHITELIST_IP environment variable and to use specific branch from your repo.


### Resources
- [phpMyAdmin documentation](https://docs.phpmyadmin.net/en/latest/config.html)
- [Creating a 'Deploy to Heroku' Button](https://devcenter.heroku.com/articles/heroku-button)
- [Using Heroku button with private repos](https://devcenter.heroku.com/articles/heroku-button#private-github-repos)
- [Heroku Error pages](https://devcenter.heroku.com/articles/error-pages)