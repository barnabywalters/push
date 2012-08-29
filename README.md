push
==============

A composer-enabled package containing various PHP classes for using Pubsubhubbub.

Current contents:

* Josh Fraser's PHP PuSH publishing client

## Installation

Install using [Composer](http://getcomposer.org). If you don't already have composer, download it per their instructions. Then:

1. Add `indieweb/push` to your project's `composer.json` file, so it looks a bit like this:
	
		{
			"require" : {
				"indieweb/push": "*"
			},
			"minimum-stability": "dev"
		}
	
	If you've never used composer, this is just specifying that your project needs the indieweb/push package in order to work, it doesn't matter which version you get, and it's all right to use packages which are in development.
1. Run `php composer.phar update`
1. Provided there were no errors, you should now have indieweb/push installed

## Usage

indieweb/push supports psr-0 autoloading, so using the classes is easy provided you're familiar with PHP namespaces.

Say you want to use the PuSH publisher (class for pinging hubs to let them know of updates):

	<?php
	// This script pings a hub
	
	use indieweb\PuSH\Publisher;
	
	$p = new Publisher('http://pubsubhubbub.appspot.com/publish');
	
	$p -> publish_update('http://domain.tld/path/to/your/feed.atom');
	
	// EOF

TODO: Add more usage examples and documentation as more classes are added