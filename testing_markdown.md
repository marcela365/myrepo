---
title: "Untitled"
output: 
  html_document: 
    keep_md: yes
---
<div class="alert alert-danger">
  <strong>Warning:</strong>
  this document contains 4 failing validations.
</div>



We can validate data inside of specialized code chunks. The **pointblank** makes this possible by loading it, as above. We'll perform some simple validations using `small_table`.



```r
small_table
```



```
## # A tibble: 13 × 8
##    date_time           date           a b             c      d e     f    
##    <dttm>              <date>     <int> <chr>     <dbl>  <dbl> <lgl> <chr>
##  1 2016-01-04 11:00:00 2016-01-04     2 1-bcd-345     3  3423. TRUE  high 
##  2 2016-01-04 00:32:00 2016-01-04     3 5-egh-163     8 10000. TRUE  low  
##  3 2016-01-05 13:32:00 2016-01-05     6 8-kdg-938     3  2343. TRUE  high 
##  4 2016-01-06 17:23:00 2016-01-06     2 5-jdo-903    NA  3892. FALSE mid  
##  5 2016-01-09 12:36:00 2016-01-09     8 3-ldm-038     7   284. TRUE  low  
##  6 2016-01-11 06:15:00 2016-01-11     4 2-dhe-923     4  3291. TRUE  mid  
##  7 2016-01-15 18:46:00 2016-01-15     7 1-knw-093     3   843. TRUE  high 
##  8 2016-01-17 11:27:00 2016-01-17     4 5-boe-639     2  1036. FALSE low  
##  9 2016-01-20 04:30:00 2016-01-20     3 5-bce-642     9   838. FALSE high 
## 10 2016-01-20 04:30:00 2016-01-20     3 5-bce-642     9   838. FALSE high 
## 11 2016-01-26 20:07:00 2016-01-26     4 2-dmx-010     7   834. TRUE  low  
## 12 2016-01-28 02:51:00 2016-01-28     2 7-dmx-010     8   108. FALSE low  
## 13 2016-01-30 11:23:00 2016-01-30     1 3-dka-303    NA  2230. TRUE  high
```



We can perform validation checks on that table with **pointblank** step functions (inside code chunks where `validate = TRUE`). The results will be initially hidden in the rendered HTML document but can be revealed.

preserve8e06e672bfef170c

We could also use **pointblank**'s `stop_if_not()` function to generate some predicate-based validation statements.

preserveae4b269582bd81a7

Note that with multiple **pointblank** step functions chained together, only the first error encountered will be reported.

preserveb456edb9bb1ed707

If all validations in a `validate` chunk do not fail, we can still inspect the validation code.

preservea220c946c7cfc0ee

We can provide a single, agent-based interrogation inside of a `validate` chunk (the reporting is visible once the `Agent Report` button is pressed). For best rendering results, don't place anything else inside the chunk. This acts as standalone reporting and will not result in document-level errors or warnings.

preserve3891db471946f16f
