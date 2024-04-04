# IonBytes Coding Standard

## Installation

1. Install via composer by running:
    ```bash
    composer require --dev ionbytes/coding-standard
    ```
2. Create the `phpcs.xml.dist` file in root path of you repository:
    ```xml
    <?xml version="1.0"?>
    <ruleset xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:noNamespaceSchemaLocation="vendor/squizlabs/php_codesniffer/phpcs.xsd">
        
        <arg name="basepath" value="."/>
        <arg name="cache" value=".phpcs-cache"/>
        <arg name="colors"/>
        <arg name="extensions" value="php"/>
        <arg name="parallel" value="80"/>
        
        <!-- Show progress -->
        <arg value="sp"/>
        
        <!-- Paths to check -->
        <file>src</file>
        <file>tests</file>
        
        <!-- Include all rules from the IonBytes Coding Standard -->
        <rule ref="IonBytes"/>
    </ruleset>
    ```
3. Add composer scripts into your `composer.json`:
    ```json lines
    {
      "scripts": {
        "cs-check": "phpcs",
        "cs-fix": "phpcbf -vpw"
      }
    }
    ```

## Usage

- To run checks only:

  ```bash
  composer run cs
  ```

- To automatically fix violations coding standards:

  ```bash
  composer run cs-fix
  ```

## License

The MIT License (MIT). Please see [License](LICENSE) for more information
