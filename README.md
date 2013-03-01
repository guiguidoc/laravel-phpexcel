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

This is all fine and works until you run it and then you will get the warning

PDF Rendering library has not been defined

You need to install a renderer and then go to

/bundles/laravel-phpexcel/PHPExcel/Settings.php

and alter these element

	/**
	 * Name of the external Library used for rendering PDF files
	 *		e.g.
	 *			mPDF
	 *
	 * @var string
	 */
	private static $_pdfRendererName = "domPDF";

	/**
	 * Directory Path to the external Library used for rendering PDF files
	 *
	 * @var string
	 */
	private static $_pdfRendererPath = "/Applications/MAMP/htdocs/dataman/public/dompdf/";

I have used domPDF. Obviously alter the path to wherever you install domPDF
n.b. i tried mPDF but had errors in it's code.
