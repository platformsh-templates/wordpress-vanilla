> [!WARNING]
> **This repository is no longer maintained by our internal teams.**  
> The template is provided *as is* and will not receive updates, bug fixes, or new features.  
> You are welcome to contribute on it or fork the repository and modify it for your own use.
> To deploy this template on [Upsun](https://www.upsun.com), you can use the command [upsun project:convert](https://docs.upsun.com/administration/cli/reference.html#projectconvert)
> on this codebase to convert the existing `.platform.app.yaml` configuration file to the [Upsun Flex format](https://docs.upsun.com/create-apps/app-reference/single-runtime-image.html).

# WordPress (Vanilla) for Platform.sh

This template builds WordPress on Platform.sh, installing WordPress to a subdirectory instead of to the project root. It does not use a package management tool like Composer, and updating core, themes, and plugins should be done with care. A custom configuration file is provided that runs on Platform.sh to automatically configure the database, so the installer will not ask you for database credentials.

WordPress is a blogging and lightweight CMS written in PHP.

## Features

* PHP 8.4
* MariaDB 11.8
* Automatic TLS certificates

## Post-install

Run through the WordPress installer as normal. You will not be asked for database credentials as those are already provided. 

## Customizations

The following changes have been made relative to Bedrock's project creation command `composer create-project roots/bedrock`. If using this project as a reference for your own existing project, replicate the changes below to your project.

* The `.platform.app.yaml`, `.platform/services.yaml`, and `.platform/routes.yaml` files have been added.  These provide Platform.sh-specific configuration and are present in all projects on Platform.sh.  You may customize them as you see fit.
* A `.environment` file has been included which sets WordPress's configuration on Platform.sh. It defines the connection to the MariaDB database, the primary site URL, and security keys and salts. 
* A base [Landofile](https://docs.lando.dev/config/lando.html#base-file) provides configuration to use this template locally using [Lando](https://docs.lando.dev).


## Local development

This template has been configured for use with [Lando](https://docs.lando.dev).  Lando is Platform.sh's recommended local development tool.  It is capable of reading your Platform.sh configuration files and standing up an environment that is _very similar_ to your Platform.sh project.  Additionally, Lando can easily pull down databases and file mounts from your Platform.sh project.

To get started using Lando with your Platform.sh project check out the [Quick Start](https://docs.platform.sh/development/local/lando.html) or the [official Lando Platform.sh documentation](https://docs.lando.dev/config/platformsh.html).

## References

* [WordPress](https://wordpress.org/)
* [WordPress on Platform.sh](https://docs.platform.sh/frameworks/wordpress.html)
* [PHP on Platform.sh](https://docs.platform.sh/languages/php.html)
* [How to install Wordpress plugins and themes with Composer](https://community.platform.sh/t/how-to-install-wordpress-plugins-and-themes-with-composer/507)
* [How to install custom/private Wordpress plugins and themes with Composer](https://community.platform.sh/t/how-to-install-custom-private-wordpress-plugins-and-themes-with-composer/622)
