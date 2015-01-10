# Cachet [![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

[![Build Status](https://img.shields.io/travis/cachethq/Cachet.svg?style=flat-square)](https://travis-ci.org/cachethq/Cachet)
[![Quality Score](https://img.shields.io/scrutinizer/g/cachethq/Cachet.svg?style=flat-square)](https://scrutinizer-ci.com/g/cachethq/Cachet)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE)
[![Gitter](https://img.shields.io/badge/gitter-join%20chat-brightgreen.svg?style=flat-square)](https://gitter.im/cachethq/Cachet?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

![Current progress](https://dl.dropboxusercontent.com/u/7323096/Cachet.png)

For more information on why I started developing Cachet, check out my [blog post](http://james-brooks.uk/cachet/?utm_source=github&utm_medium=readme&utm_campaign=github-cachet), for more read [What's next for Cachet?]([What's next for Cachet?](http://james-brooks.uk/whats-next-for-cachet/)) [A demo, deployed to Heroku](https://cachet.herokuapp.com).

**Currently in development. Things may change or break until a solid release has been announced.**

## Features

- List your services components.
- Log incidents.
- Override status page colors.
- Apply a custom stylesheet to the status page.
- Markdown support for incident messages.
- RESTful API.
- Multilingual.

## Requirements

- PHP 5.4 or newer
- Composer
- Node.js
    + Bower
    + Gulp
- mcrypt extension

## Installation

See the [INSTALL.md](/docs/setup/install.md) document for more information. If you'd like to add more documentation, please create a Pull Request, I'd be happy to merge!

[Deploying to Heroku](/docs/setup/install.md#deploy-to-heroku) requires one-click to get started and no knowledge of PHP or Laravel afterwards.

## Running via Docker

Run a DB container:

    export DB_USERNAME=cachet
    export DB_PASSWORD=cachet
    export DB_DATABASE=cachet
    docker run --name mysql -e MYSQL_USER=$DB_USERNAME -e MYSQL_PASSWORD=$DB_PASSWORD -e MYSQL_DATABASE=$DB_DATABASE -d mysql

Initialize the DB if you havent yet:

    docker run --link mysql:mysql -e DB_HOST=mysql -e DB_DATABASE=$DB_DATABASE -e DB_USERNAME=$DB_USERNAME -e DB_PASSWORD=$DB_PASSWORD byxorna/cachet:test php artisan migrate

Run Cachet:

    docker run -d --link mysql:mysql -p 80:80 -e DB_HOST=mysql -e DB_DATABASE=$DB_DATABASE -e DB_USERNAME=$DB_USERNAME -e DB_PASSWORD=$DB_PASSWORD byxorna/cachet:test 

Now go to http://localhost/setup and type things

## Translations

A special thank you to our [translators](https://crowdin.com/project/cachet/activity_stream), who have allowed us to share Cachet with the world. If you'd like to contribute translations, please check out our [CrowdIn project](https://crowdin.com/project/cachet).

## License

Cachet is licensed under [The MIT License (MIT)](LICENSE).
