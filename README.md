# KEC PHPCS Configuration

Composer library to provide drop in installation and configuration of PHPCS, setting reasonable defaults for development with nearly zero configuration.

## Installation
Add this repo to composer repositories list as vcs

https://github.com/alexsancho/phpcs-composer.git

Install the library via Composer:

```bash
$ composer require --dev alexsancho/phpcs-composer:dev-master
```

## Usage
Lint your PHP files with the following command:

```bash
$ ./vendor/bin/phpcs  --standard=phpcs.xml --runtime-set text_domain theme-text-domain,default .
```

If relying on Composer, edited the `composer.json` file by adding the following:

```json
	"scripts": {
    "lint": "vendor/bin/phpcs --standard=phpcs.xml --runtime-set text_domain theme-text-domain .",
		"fix": "vendor/bin/phpcbf --standard=phpcs.xml --runtime-set text_domain theme-text-domain ."
	}
```

### IDE Integration

Some IDE integrations of PHPCS fail to register the `kec-Default` ruleset. In order to rectify this, place `.phpcs.xml.dist` at your project root:

```xml
<?xml version="1.0"?>
<ruleset name="Project Rules">
	<rule ref="kec-Default" />
</ruleset>
```
