# Warning

This bundle currently only work for the Microsoft botframework.

# Requirement

Symfony 4


# Installation

Install the symfoy bundle using composer
```console
composer require maalls/botman-bundle
```

Add your bot framework credentials.
```.env
BOTFRAMEWORK_APP_ID=*******************
BOTFRAMEWORK_PASSWORD=*****************
```

# Example

Create the bot via autowiring:

```php

    // in src/Service/MyService.php

    function __construct(\Maalls\BotManBundle\Service\Factory $factory) {

        $bot = $factory->createBot(); // \BotMan\BotMan\BotMan with BotFramwork driver.

        $bot->hears("(.*)", function($bot, $message) {

            $bot->reply("Anyway, hello.");

        });

    }
```

# Testing

```console 
./vendor/bin/phpunit tests/
```

