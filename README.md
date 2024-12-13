# Wacloud WhatsApp API for Laravel

This package integrates Wacloud's WhatsApp API into your Laravel application.

## Installation
```bash
composer require rumipro/wacloud-whatsapp
```

## Configuration
Publish the config file:
```bash
php artisan vendor:publish --tag=config
```

Set the `WACLOUD_WHATSAPP_API_KEY` in your `.env` file.

## Usage
```php
use WacloudWhatsApp;

// Send a message
$response = WacloudWhatsApp::sendMessage(
    '88017xxxxxxxx',
    'Hello from Laravel WhatsApp API',
    null, // Leave null for text-only messages
    'QRLKQ28424D5E38'
);

if ($response['success']) {
    echo $response['message'];
} else {
    echo "Error: {$response['message']} (Code: {$response['code']})";
}
```