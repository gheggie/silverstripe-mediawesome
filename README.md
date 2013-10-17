# mediawesome

	A module for SilverStripe which will allow creation of dynamic media holders/pages with CMS
	customisable types and attributes (blogs, events, news, publications).

## Requirement

* SilverStripe 3.1.X

## Getting Started

* Place the module under your root project directory.
* `/dev/build`
* Create a media holder.
* Configure the media type.
* Create media pages.

## Overview

### Default Media Types

These are the default media types and their respective attributes.

```php
array(
	'Blog' => array(
		'Author'
	),
	'Event' => array(
		'Start Time',
		'End Time',
		'Location'
	),
	'News' => array(
		'Author'
	),
	'Publication' => array(
		'Author'
	)
);
```

Apply custom default media types with respective attributes, or additional attributes to existing default types.

```php
MediaPage::customise_defaults(array(
	'Media Type' => array(
		'Attribute'
	)
));
```

These may also be added through the CMS, depending on the current user permissions.

* Select a media holder.
* Select `Media Types`

### Dynamic Media Attributes

These may be customised through the CMS, depending on the current user permissions.

* Select a media holder.
* Select `Media Types`
* Select the respective type.

These will be applied to new and existing media pages of the respective type.

### Media Tags

* Select a media holder.
* Select `Media Tags`

### CMS Permissions

These may be changed through the site configuration by an administrator.

* Select `Settings`
* Select `Access`

Customisation of media types and their respective attributes will be restricted.

### Smart Templating

Custom media type templates may be defined for your media holder/page:

`MediaHolder_Blog.ss` or `MediaPage_Blog.ss`

Retrieve a specific media page attribute in templates:

```php
$getAttribute('Author')
```

### Filtering Media Pages

A media holder request may have optional date/tag filters, which are extendable by developers.

Retrieve the date filter form in templates:

```php
$dateFilterForm
```

To see templating examples, look at:

`MediaHolder.ss` and `MediaPage.ss`

## Maintainer Contact

	Nathan Glasl, nathan@silverstripe.com.au
