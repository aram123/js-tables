# Show an interactive table with filters #

```
<script src="jquery.table.js"></script>
<script>
var data = [
  [ "Tag", "Count" ],
  [ "DIV", 100     ],
  [ "A",   90      ],
  [ "IMG", 80      ]
];

// Show this table on the <div id="table"> element
jQuery("div#table").table(data);

// Show a CSV file
jQuery.get(csvfile, function(data) {
    jQuery("div#table").table(jQuery.csv()(data));
});
</script>
```

The table displayed can be filtered using regular expressions.

You only see 100 rows at a time. As the user scrolls down, subsequent rows are displayed. This makes it ideal for displaying and searching large tables.