# Laravel PHPExcel Bundle

---

OpenXML - Read, Write and Create Excel documents in PHP - Spreadsheet engine

---

Project providing a set of classes for the PHP programming language, which allow you to write to and read from different spreadsheet file formats, like Excel (BIFF) .xls, Excel 2007 (OfficeOpenXML) .xlsx, CSV, Libre/OpenOffice Calc .ods, Gnumeric, PDF, HTML, ... This project is built around Microsoft's OpenXML standard and PHP.

---

## Installation

Run this command on the CLI:

    php artisan bundle:install laravel-phpexcel

### Registering the Bundle

Place the following code in ``application/bundles.php``:


    'laravel-phpexcel'    => array(
        'auto'        => true
    )


### Usage ####

		$objPHPExcel = new PHPExcel();
		$sheet = $objPHPExcel->getActiveSheet();
		$sheet->setCellValue('A1','Test value');
		$writer = new PHPExcel_Writer_PDF($objPHPExcel);
		$writer->save("test.xlsx");
		return Response::download('test.xlsx', 'test.xlsx');


More info about PHPExcel , visit : http://phpexcel.codeplex.com/
