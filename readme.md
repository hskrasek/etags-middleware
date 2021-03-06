etags-middleware
================

A HttpKernelInterface middleware for adding ETag headers based on response content. This package should work with StackPHP HttpKernelInterface Frameworks.

## Install

Via Composer

``` json
{
    "require": {
        "aranw/etags-middleware": "dev-master"
    }
}
```

## Example

Silex example

``` php
<?php

$app = new Silex\Application();

$app->get('/', function () {
    return 'Hello World';
});

$stack = new Stack\Builder();
$stack->push('Aranw\ETagsMiddleware\ETags');

$app = $stack->resolve($app);

```

## Usage 

Currently you can either install this using the provided Laravel Service Provider or by using the StackPHP's Builder class like the example above.

## Todo


This is still in its earliest stages of development, and below is a list of issues that still need resolving:

- [ ] Add tests
- [ ] Explore usage of Last-Modified header and how it can be added to work in this package and how it affects the ETag header
- [ ] Add more service providers for other frameworks
- [ ] Expore usage of custom options to provide ability to exclude or include URLs, or URL Regex Patterns 

## Inspiration

Inspiration from rack etag middleware
