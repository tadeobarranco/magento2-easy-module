# How to bootstrap a Magento 2 module

In this repository I want to illustrate basics to bootstrap a Magento 2 module step by step.

As you may know Magento 2 modules contains all the module's files in just one folder following the next [file structure](https://devdocs.magento.com/guides/v2.3/extension-dev-guide/build/module-file-structure.html#module-file-structure):

```
VendorName/
  ModuleName/
    Api/
    Block/
    Controller/
    Console/
    etc/
    Helper/
    i18n/
    Model/
    Plugin/
    Test/
    view/
    composer.json
    LICENSE.txt
    LICENSE_ALF.txt
    README.md
    registration.php
```

The above Magento 2 file structure has [common](https://devdocs.magento.com/guides/v2.3/extension-dev-guide/build/module-file-structure.html#common-directories) and [additional](https://devdocs.magento.com/guides/v2.3/extension-dev-guide/build/module-file-structure.html#additional-directories) directories but to **bootstrap a Magento 2 module** the [required files](https://devdocs.magento.com/guides/v2.3/extension-dev-guide/build/module-file-structure.html#required-files) are `registration.php`, `etc/module.xml` and `composer.json`.

> Remember that Magento 2 modules **lives** in two possible paths which are `app/code/VendorName/ModuleName` and `vendor/vendor-name/module-name`. Difference between both is that as you can use composer to install modules these are placed into the `vendor` directory while into `app/code` are the modules that you develop. 

Let's create the module for this repository and its required files. In my case the `VendorName` is represented by **Barranco** and the `ModuleName` is **EasyModule**. Having said that I had the following file structure:

```
app/
  code/
    Barranco/
      EasyModule/
```

Let's add the [registration.php](https://github.com/tadeobarranco/magento2-easy-module/commit/b8a0320) file whit the following content:

```php
<?php

\Magento\Framework\Component\ComponentRegistrar::register(
    \Magento\Framework\Component\ComponentRegistrar::MODULE,
    'Barranco_EasyModule',
    __DIR__
);
```

In this file you implement the `register` method from the `\Magento\Framework\Component\ComponentRegistrar` class which expects three parameters: `type`, `componentName` and `path`.

The **type** parameter use a constant defined in the **ComponentRegistrar** class and means 'module' as you can bootstrap more Magento 2 component types.

In my case I set **Barranco_EasyModule** as the **componentName** defined by the name of the company which provides the module and the name of the module joined by an underscore.

AS the last parameter to register a module you set **__DIR__** as the value which means the **current script's directory**
