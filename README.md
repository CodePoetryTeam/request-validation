# codepoetry/request-validation

REST Payload Validation for PHP Applications

[![License](https://img.shields.io/badge/license-Proprietary-brightgreen.svg)](LICENSE)

## Description

`codepoetry/request-validation` is a PHP library that provides functionality for validating REST API payloads in PHP applications. It helps you ensure that incoming data adheres to your specified rules and constraints, making your applications more robust and secure.

## Installation

You can install this package via [Composer](https://getcomposer.org/):

```bash
composer require codepoetry/request-validation
```

## Requirements

- PHP >= 8.2

## Usage

Here's a basic example of how to use this package:
Create `ExampleRequest.php` file in `api_gateway/app/Http/Requests`
```php
<?php

namespace App\Http\Requests;

use Codepoetry\RequestValidation\RequestAbstract;

class ExampleRequest extends RequestAbstract
{
    /**
     * Determine if the user is authorized to make this request.
     *
     * @return bool
     */
    public function authorize(): bool
    {
        return true;
    }

    /**
     * Get the validation rules that apply to the request.
     *
     * @return array
     */
    public function rules(): array
    {
        return [
            "email" => "require"
        ];
    }

    /**
     * Get custom messages for validator errors.
     *
     * @return array
     */
    public function messages(): array
    {
        return [
            "email.unique" => trans('validation.email_unique'),
        ];
    }
}
```

## Documentation

For detailed documentation and examples, please refer to the [official documentation](https://example.com/documentation).

## License

This package is proprietary software. See the [LICENSE](LICENSE) file for licensing information.

## Author

- **Manab Roy** - [codepoetryindia@gmail.com](mailto:codepoetryindia@gmail.com) - [Manab's Website](https://example.com/manab-roy)

## Contributing

Contributions are welcome! Please see our [Contribution Guidelines](CONTRIBUTING.md) for more details.

## Issues

If you discover any issues or have questions, please feel free to open an issue in the [issue tracker](https://github.com/codepoetry/request-validation/issues).

## Changelog

See the [CHANGELOG.md](CHANGELOG.md) file for information on recent changes.

## Acknowledgments

- Special thanks to [contributors](CONTRIBUTORS.md) who have helped improve this project.
