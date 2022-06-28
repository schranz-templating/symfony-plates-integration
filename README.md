# Schranz Template Renderer Integration for Plates

Integrate the templating [Plates Bridge](https://github.com/schranz-templating/plates-bridge) 
into the Symfony Framework.

Part of the [Schranz Templating Project](https://github.com/schranz-templating/templating).

## Installation

Install this package via Composer:

```bash
composer require schranz-templating/symfony-plates-integration
```

Register the Bundle class in your `config/bundles.php` or Kernel file:

```php
return [
    // ...
    Schranz\Templating\Integration\Symfony\Plates\SchranzTemplatingPlatesBundle::class => ['all' => true],
];
```

## Configuration

The Plates Integration has the following configuration available:

```yaml
schranz_templating_plates:
    default_path: '%kernel.project_dir%/templates'
    paths: []
```

None of the configuration is required.

### default_path

**type:** `string` **default:** `'%kernel.project_dir%/templates'`

The path to the directory where Symfony will look for the application Plates templates by default.
If you store the templates in more than one directory, use the paths option too.

### paths

**type:** `array` **default:** `[]`

```yaml
schranz_templating_plates:
    paths:
        'email/default/templates': ~
        'backend/templates': 'admin'
```

Defines the directories where application templates are stored in addition to the directory defined in the [`default_path`](#default_path) option:
