# Yireo ExtensionChecker
This extension validates the code of other extensions and is complementary to static code analysis tools like PHPCS.

    ./bin/magento yireo:extensionchecker:scan Yireo_Example

## Deprecated dependencies
Class dependencies (injected via the constructor) are inspected to see if they are deprecated, for the used Magento version.

## Undeclared dependencies
Class dependencies (injected via the constructor) are traced back to their corresponding module (or the framework or something else), which should be reflected upon in the `composer.json` file and the `module.xml` file.

## @todo: Incorrect versioning for dependencies
When loading dependencies in `composer.json`, semantic versioning should be used to identify the right release for your dependency (major, minor, patch). A wildcard `*` is definitely forbidden.

## @todo: Hard-coded Proxies
A Proxy is a DI trick which should be configured in the `di.xml` file of a module and not be hard-coded in PHP.