# CodeMonster UI for Annabel Razor

Composer adapter providing CodeMonster UI components and packaged frontend assets for Annabel
Razor.

[Releases on Packagist](https://packagist.org/packages/codemonster-ru/ui-razor).

## Requirements

- PHP 8.2 or newer.
- `codemonster-ru/razor` 2.1 or newer within the 2.x line.

## Get started

```bash
composer require codemonster-ru/ui-razor:^1.1.0
```

The package does not require Node.js in production.

Register the CodeMonster UI provider during application bootstrap:

```php
use Codemonster\Razor\Components\ComponentRegistry;
use Codemonster\Ui\UiComponentProvider;

$components = new ComponentRegistry();
$components->register(new UiComponentProvider());
```

The provider owns the `cm` prefix. Components are available through tags such as `<cm-button>`.

Packaged frontend artifacts can be copied to an application public directory without Node.js:

```php
use Codemonster\Ui\Assets\AssetManifest;
use Codemonster\Ui\Assets\AssetPublisher;

$publisher = new AssetPublisher(AssetManifest::packaged());
$publishedPaths = $publisher->publish(__DIR__ . '/public/vendor/codemonster-ui');
```

Every file is declared by the package manifest and verified by SHA-256 before publication.
The packaged `css/tokens/tokens.css` and `css/css/styles.css` entries are the complete stylesheet
pair; keep their relative imported files together when serving them directly.

## Documentation

These guides link to the CodeMonster UI revision from which this package snapshot was split.

See the cross-platform [Button guide](https://github.com/codemonster-ru/ui/blob/5549b614256666fcd989b00ba1dd401111a70372/docs/components/button.md) for complete Vue and Annabel
Razor usage.
See the [Card guide](https://github.com/codemonster-ru/ui/blob/5549b614256666fcd989b00ba1dd401111a70372/docs/components/card.md) for nested default and named-slot composition.
See the [form components guide](https://github.com/codemonster-ru/ui/blob/5549b614256666fcd989b00ba1dd401111a70372/docs/components/forms.md) for native submission, choice controls, and server rerender.
See the [Accordion guide](https://github.com/codemonster-ru/ui/blob/5549b614256666fcd989b00ba1dd401111a70372/docs/components/accordion.md) for runtime installation and progressive enhancement.
See the [display components guide](https://github.com/codemonster-ru/ui/blob/5549b614256666fcd989b00ba1dd401111a70372/docs/components/display.md) for the non-interactive display cohort.
See the [navigation components guide](https://github.com/codemonster-ru/ui/blob/5549b614256666fcd989b00ba1dd401111a70372/docs/components/navigation.md) for Link, Breadcrumbs, and progressive enhancement.
See the [overlay components guide](https://github.com/codemonster-ru/ui/blob/5549b614256666fcd989b00ba1dd401111a70372/docs/components/overlays.md) for server-rendered Dialog, Drawer, Popover, and Tooltip usage.
See the [advanced input guide](https://github.com/codemonster-ru/ui/blob/5549b614256666fcd989b00ba1dd401111a70372/docs/components/advanced-inputs.md) for native form submission and CommandPalette enhancement.
See the [Table and DataTable guide](https://github.com/codemonster-ru/ui/blob/5549b614256666fcd989b00ba1dd401111a70372/docs/components/data-tables.md) for trusted table composition and server-owned data requests.
See the [layout primitives guide](https://github.com/codemonster-ru/ui/blob/5549b614256666fcd989b00ba1dd401111a70372/docs/components/layout-primitives.md) for trusted semantic
composition with Container, Stack, Inline, Section, and Grid.

## Development

```bash
composer install
composer check
```

`composer check` runs PHPStan at maximum level followed by PHPUnit.

Follow the [contribution guide](./CONTRIBUTING.md) to propose changes.
Report vulnerabilities through the [security policy](./SECURITY.md).

## License

[MIT](./LICENSE)
