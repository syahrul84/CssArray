# CssArray
PHP: Convert CSS to PHP array

Example usage:

	include('CssArray.php');
	$css = file_get_contents($file);
	$ca = new CssArray();
	$cssArray = $ca->convert($css);
	print_r($cssArray);

If you are using base64 image, and want to get the image, you will need to replace the string, for example:-

	$image = $cssArray['.container']['background-image'];
	$image = str_replace('#&', ';', $image);

Sample CSS file:

	body {
	  padding-left: 11em;
	  font-family: Georgia, "Times New Roman",
		Times, serif;
	  color: purple;
	  background-color: #d8da3d }
	ul.navbar {
	  list-style-type: none;
	  padding: 0;
	  margin: 0;
	  position: absolute;
	  top: 2em;
	  left: 1em;
	  width: 9em }
	h1 {
	  font-family: Helvetica, Geneva, Arial,
		SunSans-Regular, sans-serif }
	ul.navbar li {
	  background: white;
	  margin: 0.5em 0;
	  padding: 0.3em;
	  border-right: 1em solid black }
	ul.navbar a {
	  text-decoration: none }
	a:link {
	  color: blue }
	a:visited {
	  color: purple }

Sample PHP Array Output:

	Array
	(
	    [a] => Array
		(
		    [:link] => Array
			(
			    [color] => blue 
			)
		    [:visited] => Array
			(
			    [color] => purple 
			)
		)
	    [body] => Array
		(
		    [padding-left] => 11em
		    [font-family] => Georgia, "Times New Roman", Times, serif
		    [color] => purple
		    [background-color] => #d8da3d 
		)
	    [h1] => Array
		(
		    [font-family] => Helvetica, Geneva, Arial, SunSans-Regular, sans-serif 
		)
	    [ul.navbar] => Array
		(
		    [list-style-type] => none
		    [position] => absolute
		    [top] => 2em
		    [left] => 1em
		    [width] => 9em 
		    [li] => Array
			(
			    [background] => white
			    [margin] => 0.5em 0
			    [padding] => 0.3em
			    [border-right] => 1em solid black 
			)
		    [a] => Array
			(
			    [text-decoration] => none 
			)
		)
	)
