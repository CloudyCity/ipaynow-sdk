# CloudyCity IPayNow Sdk

[![Latest Version on Packagist][ico-version]][link-packagist]
[![Software License][ico-license]](LICENSE.md)
[![Build Status][ico-travis]][link-travis]
[![StyleCI][ico-styleci]][link-styleci]
[![Quality Score][ico-code-quality]][link-code-quality]
[![Total Downloads][ico-downloads]][link-downloads]

## Installation
```bash
composer require cloudycity/ipaynow-sdk:*
```

## Requirement
- PHP 5.6 +

## Usage
```php
use CloudyCity\IPayNowSDK\IPayNow;
use CloudyCity\IPayNowSDK\Exceptions\Exceptions;
use CloudyCity\IPayNowSDK\Exceptions\InvalidSignException;

$config = [
    'appid' => '123456789012345',
    'key' => 'abcdefghijklmnopqrstuvwxyz123456789012',
    'notify_url' => 'http://cloudycity.me/notify.php',
    'return_url' => 'http://cloudycity.me/return.php',
];

$order = [
    'money' => 600,
    'attach' => '',    // 可选
    'detail' => '',    // 可选
    'ip' => '0.0.0.0', // 可选
];

// 拉起支付
try {
    $url = IPayNow::wechat($config)->pre($order);
    $url = IPayNow::ali($config)->pre($order);
} catch (Exceptions $e) {
     //
}

// 校验回调
try {
    PayNow::wechat($config)->verify();
    PayNow::ali($config)->verify();
} catch (InvalidSignException $e) {
    //
}

```

## License

MIT

[ico-version]: https://img.shields.io/packagist/v/cloudycity/ipaynow-sdk.svg?style=flat-square
[ico-license]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square
[ico-travis]: https://img.shields.io/travis/cloudycity/ipaynow-sdk/master.svg?style=flat-square
[ico-code-coverage]: https://img.shields.io/scrutinizer/coverage/g/cloudycity/ipaynow-sdk.svg?style=flat-square
[ico-styleci]: https://styleci.io/repos/352580171/shield?branch=master
[ico-code-quality]: https://img.shields.io/scrutinizer/g/cloudycity/ipaynow-sdk.svg?style=flat-square
[ico-downloads]: https://img.shields.io/packagist/dt/cloudycity/ipaynow-sdk.svg?style=flat-square

[link-packagist]: https://packagist.org/packages/cloudycity/ipaynow-sdk
[link-travis]: https://travis-ci.org/cloudycity/ipaynow-sdk
[link-code-coverage]: https://scrutinizer-ci.com/g/cloudycity/ipaynow-sdk/code-structure
[link-styleci]: https://styleci.io/repos/352580171
[link-code-quality]: https://scrutinizer-ci.com/g/cloudycity/ipaynow-sdk
[link-downloads]: https://packagist.org/cloudycity/ipaynow-sdk
[link-author]: https://github.com/cloudycity