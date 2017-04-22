# CakePHP Translate Plugin

A CakePHP 3.x Plugin for managing translations DB driven.

Note: **Plugin in BETA version**

## Key features
- Import from POT, PO files or DB.
- Web-based and without external dependencies.
- Translate strings in all languages simultaneously.
- Allow others to help translating without having to know technical details.
- Auto-Translate and Auto-Suggest with Translate APIs (e.g. Google Translate PHP/JS) for performance.

## Benefits over normal PO editing
- Prevent duplicates, missing translations, collisions.
- Auto-Features like `trim()`, `h()`, newlines to `<p>/<br>`, espacing of `%s`.
- Validate placeholders (`{0}`, ...).
- Auto-Add Controller names (singular + plural).
- Manage in Groups (=Domains) and export/enable/disable them.
- Creates clean PO files with all translations in usage to easier diff changes.

## Installation
Including the plugin is pretty much as with every other CakePHP plugin:

```bash
composer require dereuromark/cakephp-translate
```

Then, to load the plugin either run the following command:

```sh
bin/cake plugin load Translate -b -r
```

or manually add the following line to your app's `config/bootstrap.php` file:

```php
Plugin::load('Translate', ['bootstrap' => true, 'routes' => true]);
```

Routes are needed for the backed, the bootstrap sets up a few defaults.

Run this in console to create the necessary DB tables: 
```
bin/cake migrations migrate -p Translate
```

## Usage
Web Backend
- Navigate to `/admin/translate/` in your browser.

CLI
- Run `bin/cake translate`.

## Tips
- Use [TinyAuth](https://github.com/dereuromark/cakephp-tinyauth) or alike to manage access to the translation backend for user groups.
- Implement your own Translation engine if you want to have even better auto-suggest.

## Configuration and documentation
- [Documentation](docs/README.md)

