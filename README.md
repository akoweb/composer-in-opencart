## 1- add or create below file into opencart folder


## 1-1- file name : composer.json


```javascript

{
  "name": "opencart/opencart",
  "description": "OpenCart",
  "type": "project",
  "keywords": [
    "opencart",
    "ecommerce",
    "framework",
    "opensource"
  ],
  "homepage": "https://www.opencart.com/",
  "license": "GPL-3.0-or-later",
  "support": {
    "email": "support@opencart.com",
    "issues": "https://github.com/opencart/opencart/issues",
    "forum": "https://forum.opencart.com/",
    "wiki": "https://github.com/opencart/opencart/wiki",
    "source": "https://github.com/opencart/opencart/releases",
    "docs": "http://docs.opencart.com/"
  },
  "config": {
    "vendor-dir": "system/storage/vendor/"
  },
  "require": {
    "scssphp/scssphp": "1.4.0",
    "php": ">=7.1.0",
    "twig/twig": "^3.0",
    "aws/aws-sdk-php": "^3.142.1",
    "phpoffice/phpspreadsheet": "^1.18",
    "phpmailer/phpmailer": "^6.5"
  }
}

```




## 2- change vendor-dir tag 

#### "vendor-dir": "system/storage/vendor/"


## 3- run composer command 

####  composer require phpoffice/phpspreadsheet


## 4- finally use the code!  added below code into your controller file.

```php

<?php
use PhpOffice\PhpSpreadsheet\Spreadsheet;
use PhpOffice\PhpSpreadsheet\Writer\Xlsx;

class ControllerCommonHeader extends Controller {
	public function index() {


        $spreadsheet = new Spreadsheet();
        $sheet = $spreadsheet->getActiveSheet();
        $sheet->setCellValue('A1', 'Hello World !');
        $writer = new Xlsx($spreadsheet);
        $writer->save(DIR_APPLICATION.'demo.xlsx');
        
        }
        
 }

```
