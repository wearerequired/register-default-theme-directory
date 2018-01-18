# Register WordPress' Default Theme Directory

When installing WordPress using Composer with a separated `wp-content` directory, WordPress isn't automatically aware of the default themes inside the WordPress folder.

This package simply registers the theme directory with WordPress so you can use the default WordPress themes without hassle.

## Installation

The package type is `wordpress-muplugin`. Example of a `composer.json`:

Example of a `composer.json` for a site:

```json
{
  "name": "wearerequired/something",
  "description": "required.com",
  "license": "GPL-2.0-or-later",
  "authors": [
    {
      "name": "required gmbh",
      "email": "info@required.ch"
    }
  ],
  "require": {
    "php": ">=5.6",
    "koodimonni/composer-dropin-installer": "dev-master",
    "johnpbloch/wordpress": "~4.9",
    "wearerequired/register-default-theme-directory": "^1.0"
  },
  "extra": {
    "wordpress-install-dir": "wordpress/wp",
    "installer-paths": {
      "wordpress/content/plugins/{$name}/": [
        "type:wordpress-plugin"
      ],
      "vendor/{$vendor}/{$name}/": [
        "type:wordpress-muplugin"
      ],
      "wordpress/content/themes/{$name}/": [
        "type:wordpress-theme"
      ]
    },
    "dropin-paths": {
      "wordpress/content/mu-plugins/": [
        "type:wordpress-muplugin"
      ]
    }
  },
  "minimum-stability": "dev",
  "prefer-stable": true
}
