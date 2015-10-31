What is DompdfBundle?
=============================
[![Latest Stable Version](http://img.shields.io/packagist/v/core23/dompdf-bundle.svg)](https://packagist.org/packages/core23/dompdf-bundle)
[![Build Status](http://img.shields.io/travis/core23/DompdfBundle.svg)](http://travis-ci.org/core23/DompdfBundle)
[![Latest Stable Version](https://poser.pugx.org/core23/dompdf-bundle/v/stable.png)](https://packagist.org/packages/core23/dompdf-bundle)
[![License](http://img.shields.io/packagist/l/core23/dompdf-bundle.svg)](https://packagist.org/packages/core23/dompdf-bundle)

This bundle provides a wrapper for using [dompdf] inside symfony.

### Installation

```
php composer.phar require core23/dompdf-bundle
```

### Enabling the bundle

```php
<?php
// app/AppKernel.php

	public function registerBundles()
	{
		return array(
			// ...

			new Core23\DompdfBundle\Core23DompdfBundle(),

			// ...
		);
	}
```

### Usage

Whenever you need to turn a html page into a pdf just use this anywhere in your controller:

```php
// Set some html and get the service
$html = '<h1>Sample Title</h1><p>Lorem Ipsum</p>';
$dompdf = $this->get('dompdf');

// Stream the pdf to the browser
$dompdf->streamHtml($html, "document.pdf");

// Get binary content of the pdf document
$dompdf->getPdf($html);
```

### Configuration

You can configure each constant starting with ``DOMPDF_`` under the ``config`` key.

```yaml
core23_dompdf:
	config:
		DOMPDF_DPI: 150
		DOMPDF_DEFAULT_PAPER_SIZE: A4
		DOMPDF_KEY_XXX: value
		...
```

This bundle is available under the [MIT license](LICENSE.md).

[dompdf]: https://github.com/dompdf/dompdf
