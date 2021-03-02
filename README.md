iTunes XML parser for PHP
==========================

#### A class to extract info, tracks and playlists from an iTunes XML file.

Original code copyright (c) 2003 by [Robert A. Wallis](https://github.com/robert-wallis).
Dicked around with in 2005 by [Peter Minarik](http://www.wirsindecht.org/),
and in 2013 by [Conan Theobald](mailto:me[at]conans[dot]co[dot]uk).

LGPL licensed: See [LICENSE](LICENSE)

## About

A simple PHP class that will read an iTunes XML file and convert the info,
tracks and playlists contained within into an array of objects.

Tracks can be matched to playlist-items by running the `#processPlaylists()`
method after opening your XML file.

Supports sorting fields by string, number, and date.

## Instructions

See [example.php](example.php) for a basic implementation.

```php
require_once 'iTunesXMLparser.class.php';

$xml_path = 'iTunes playlist export.xml';

$itunes = new iTunesXMLParser();
$itunes->sort_field = 'Track ID';
$itunes->sort_direction = 'ascending';
$itunes->open( $xml_path );

/*
  "$itunes->data" is now available. print_r to see what's inside:
    print_r( $itunes->data );
*/

```

For conversion to JSON, I recommend using the `jsbeautifier.org`
[PHP port](https://github.com/einars/js-beautify/tree/attic-php/php).

## Credits

Based on work by:

*   Robert Wallis
*   http://www.wirsindecht.org/
