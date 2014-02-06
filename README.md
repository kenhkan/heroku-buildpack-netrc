Write to ~/.netrc
=================

Simply have a `NETRC_HOST`, `NETRC_USERNAME`, and `NETRC_PASSWORD` as the
environment variables and they would be written to `~/.netrc`.


Requirements
------------

The app must have `user-env-compile` enabled for the buildpack to have access to config vars when building.

    heroku labs:enable user-env-compile -a myapp

[Read more aobut user-env-compile.](https://devcenter.heroku.com/articles/labs-user-env-compile)


Usage
-----

Example usage:

    $ heroku create --stack cedar --buildpack http://github.com/fs-webdev/heroku-buildpack-netrc.git

Enable config vars to be visible during buildpack execution, and set the token.

    $ heroku labs:enable user-env-compile
    $ heroku config:set GITHUB_AUTH_TOKEN=<my-read-only-token>

Deploy your app.

    $ git push heroku master  # push your changes to Heroku
