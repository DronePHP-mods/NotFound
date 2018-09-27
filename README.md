# NotFound module for DronePHP
### Make it easy

This software is a module for [DronePHP](https://github.com/Pleets/DronePHP).

Visit [DronePHP official](http://www.dronephp.com)

## Installation

Change your index.php to

```php
try
{
    $config = include "config/application.config.php";
    $mvc = new Drone\Mvc\Application($config);
    $mvc->run();
}
# to load only the error view
catch (Drone\Mvc\Exception\ViewNotFoundException $e)
{
    $mvc->getRouter()->setIdentifiers('NotFound', 'Error', 'notFoundView');
    $mvc->getRouter()->run();
}
# to load the error template
catch (Drone\Mvc\Exception\PageNotFoundException $e)
{
    $mvc->getRouter()->setIdentifiers('NotFound', 'Error', 'notFound');
    $mvc->getRouter()->run();
}
```
