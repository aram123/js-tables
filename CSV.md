# Convert CSV data into arrays #

```
<script src="jquery.csv.js"></script>
<script>
// Convert CSV data into array of arrays
jQuery.csv()("1,2,3\n4,5,6\n7,8,9\n"); // = [ [1,2,3], [4,5,6], [7,8,9] ]

// It handles quotes
jQuery.csv()('a,"b,c",d'); // = [ ['a', 'b,c', 'd'] ]

// You can use any delimiter, e.g. tab
jQuery.csv("\t")("a\tb\nc\td\n"); // = [ ['a','b'], ['c','d'] ]

// Quick usage with AJAX:
jQuery.get(csvfile, function(data) { array = jQuery.csv()(data); });

// Using across multiple files
var getTSV = jQuery.csv("\t");
jQuery.get(csvfile1, function(data) { array1 = getTSV(data); });
jQuery.get(csvfile2, function(data) { array2 = getTSV(data); });
...
</script>
```

# Parameters #
`jQuery.csv(delim, quote, linedelim)`
| delim | column delimiter | Comma by default. Use "\t" for tab delimited files. Use "\t,\|" to use any of TAB, comma or pipe |
|:------|:-----------------|:-------------------------------------------------------------------------------------------------|
| quote | quote character  | Double quote by default. Use "'\"" for either single or double quote                             |
| linedelim | row delimiter    | "\r\n" by default. Use "\r\n\|" to specify any of "\r", "\n" or pipe                             |