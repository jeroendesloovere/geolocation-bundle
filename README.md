# Geolocation bundle

This Geolocation Symony2 Bundle uses the geolocation-php-api class using Google Maps API which finds latitude/longitude from an address or reverse.

## Usage

### Installation

``` json
{
    "require": {
        "jeroendesloovere/geolocation-bundle": "1.0.*"
    }
}
```
> Adding this code in your `composer.json` file will get the [latest :package_name Packagist package](https://packagist.org/packages/jeroendesloovere/geolocation-bundle using [Composer](https://getcomposer.org).

and in app/AppKernel.php
```php
public function registerBundles()
{
    $bundles = array(
        // ...,
        new JeroenDesloovere\Bundle\GeolocationBundle\JeroenDesloovereGeolocationBundle()
    );
}
```

### Example

```php
$geolocation = $this->get('jeroendesloovere.geolocation');

// define result
$result = $geolocation::getCoordinates('Koningin Maria Hendrikaplein', '1', 'Gent', '9000', 'belgië');

// dump result
echo 'Coordinates = ' . $result['latitude'] . ', ' . $result['longitude'] . '<br/>';

// define result: @return array(label, street, streetNumber, city, cityLocal, zip, country, countryLabel)
$result = $geolocation::getAddress(51.0363935, 3.7121008);

// define result
echo 'Address = ' . $result['label'] . '<br/>';
```
