# CssArray
PHP: Convert CSS to PHP array

Example usage:

	include('CssArray.php');

	$css = file_get_contents($file);
	
	$ca = new CssArray();
	
	$cssArray = $ca->convert($css);
	
	print_r($cssArray);
