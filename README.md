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
