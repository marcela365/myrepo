---
title: "Untitled"
output:
  pdf_document: default
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
## # A tibble: 13 x 8
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

<!--html_preserve-->
<div class="pointblank-badge-container-inner" style="text-align: center; padding-bottom: 12px; font-size: 16px;">
  <span class="pointblank-badge label label-danger" data-toggle="collapse" data-target="#chunk-1870669" aria-expanded="false" aria-controls="chunk-1870669" style="cursor: pointer;">2 validations failed.</span>
</div>
<div id="chunk-1870669" class="pointblank-chunk panel panel-danger collapse" >
  <div class="panel" style="margin-bottom: 0px;">
    <div class="panel-body" style="padding-left: 18px; padding-top: 18px; padding-right: 18px; padding-bottom: 0px; background: #FAFAFA;">
      <div class="panel panel-success">
  <div class="panel-heading" style="color:#333;border-color:transparent;">
    <div style="display:inline-flex;width:100%;">
      <div style="margin-top:2px;padding-left:5px;background:#FAFAFA;"><svg height="1.5em" viewBox="0 0 32 32" style="margin-top: 1px; fill: green;"><path d="M 28.28125 6.28125 L 11 23.5625 L 3.71875 16.28125 L 2.28125 17.71875 L 10.28125 25.71875 L 11 26.40625 L 11.71875 25.71875 L 29.71875 7.71875 Z"></path></svg></div>
      <div style="padding-left:2px;padding-right:2px;padding-top:2px;padding-bottom:4px;margin-top:2px;background:#FAFAFA;width:100%;overflow-x:scroll;">
        <code style="background-color:#FAFAFA;padding-left:0;">col_exists(small_table, columns = vars(a, b, c, d, e, f))</code>
      </div>
    </div>
  </div>
</div><div class="panel panel-danger">
  <div class="panel-heading" style="color:#333;border-color:transparent;">
    <div style="display:inline-flex;width:100%;">
      <div style="margin-top:2px;padding-left:5px;background:#FAFAFA;"><svg height="1.5em" viewBox="0 0 32 32" style="margin-top: 3px; fill: red;"><path d="M 16 3 C 8.832031 3 3 8.832031 3 16 C 3 23.167969 8.832031 29 16 29 C 23.167969 29 29 23.167969 29 16 C 29 8.832031 23.167969 3 16 3 Z M 16 5 C 22.085938 5 27 9.914063 27 16 C 27 22.085938 22.085938 27 16 27 C 9.914063 27 5 22.085938 5 16 C 5 9.914063 9.914063 5 16 5 Z M 12.21875 10.78125 L 10.78125 12.21875 L 14.5625 16 L 10.78125 19.78125 L 12.21875 21.21875 L 16 17.4375 L 19.78125 21.21875 L 21.21875 19.78125 L 17.4375 16 L 21.21875 12.21875 L 19.78125 10.78125 L 16 14.5625 Z"/></svg></div>
      <div style="padding-left:2px;padding-right:2px;padding-top:2px;padding-bottom:4px;margin-top:2px;background:#FAFAFA;width:100%;overflow-x:scroll;">
        <code style="background-color:#FAFAFA;padding-left:0;">rows_distinct(small_table, vars(d, e))</code>
      </div>
    </div>
    <hr style="margin-top:10px;margin-bottom:0;border:1px solid #EBCCD1;"/>
    <div class="panel-body" style="padding-left:13px;padding-top:15px;padding-right:13px;padding-bottom:15px;background:#FAFAFA;width:100%;overflow-x:scroll;">
      <code style="background-color:#FAFAFA;padding-left:0;overflow-x:scroll;">## Error: Exceedance of failed test units where there weren't distinct rows across all columns.
## The `rows_distinct()` validation failed beyond the absolute threshold level (1).
## * failure level (2) &gt;= failure threshold (1)</code>
    </div>
    <hr style="margin-top:0;margin-bottom:0;border:1px solid #EBCCD1;"/>
  </div>
</div><div class="panel panel-danger">
  <div class="panel-heading" style="color:#333;border-color:transparent;">
    <div style="display:inline-flex;width:100%;">
      <div style="margin-top:2px;padding-left:5px;background:#FAFAFA;"><svg height="1.5em" viewBox="0 0 32 32" style="margin-top: 3px; fill: red;"><path d="M 16 3 C 8.832031 3 3 8.832031 3 16 C 3 23.167969 8.832031 29 16 29 C 23.167969 29 29 23.167969 29 16 C 29 8.832031 23.167969 3 16 3 Z M 16 5 C 22.085938 5 27 9.914063 27 16 C 27 22.085938 22.085938 27 16 27 C 9.914063 27 5 22.085938 5 16 C 5 9.914063 9.914063 5 16 5 Z M 12.21875 10.78125 L 10.78125 12.21875 L 14.5625 16 L 10.78125 19.78125 L 12.21875 21.21875 L 16 17.4375 L 19.78125 21.21875 L 21.21875 19.78125 L 17.4375 16 L 21.21875 12.21875 L 19.78125 10.78125 L 16 14.5625 Z"/></svg></div>
      <div style="padding-left:2px;padding-right:2px;padding-top:2px;padding-bottom:4px;margin-top:2px;background:#FAFAFA;width:100%;overflow-x:scroll;">
        <code style="background-color:#FAFAFA;padding-left:0;">col_vals_gt(small_table, vars(d), 1000)</code>
      </div>
    </div>
    <hr style="margin-top:10px;margin-bottom:0;border:1px solid #EBCCD1;"/>
    <div class="panel-body" style="padding-left:13px;padding-top:15px;padding-right:13px;padding-bottom:15px;background:#FAFAFA;width:100%;overflow-x:scroll;">
      <code style="background-color:#FAFAFA;padding-left:0;overflow-x:scroll;">## Error: Exceedance of failed test units where values in `d` should have been &gt; `1000`.
## The `col_vals_gt()` validation failed beyond the absolute threshold level (1).
## * failure level (6) &gt;= failure threshold (1)</code>
    </div>
    <hr style="margin-top:0;margin-bottom:0;border:1px solid #EBCCD1;"/>
  </div>
</div>
    </div>
  </div>
</div>
<!--/html_preserve-->

We could also use **pointblank**'s `stop_if_not()` function to generate some predicate-based validation statements.

<!--html_preserve-->
<div class="pointblank-badge-container-inner" style="text-align: center; padding-bottom: 12px; font-size: 16px;">
  <span class="pointblank-badge label label-danger" data-toggle="collapse" data-target="#chunk-9554318" aria-expanded="false" aria-controls="chunk-9554318" style="cursor: pointer;">1 validation failed.</span>
</div>
<div id="chunk-9554318" class="pointblank-chunk panel panel-danger collapse" >
  <div class="panel" style="margin-bottom: 0px;">
    <div class="panel-body" style="padding-left: 18px; padding-top: 18px; padding-right: 18px; padding-bottom: 0px; background: #FAFAFA;">
      <div class="panel panel-success">
  <div class="panel-heading" style="color:#333;border-color:transparent;">
    <div style="display:inline-flex;width:100%;">
      <div style="margin-top:2px;padding-left:5px;background:#FAFAFA;"><svg height="1.5em" viewBox="0 0 32 32" style="margin-top: 1px; fill: green;"><path d="M 28.28125 6.28125 L 11 23.5625 L 3.71875 16.28125 L 2.28125 17.71875 L 10.28125 25.71875 L 11 26.40625 L 11.71875 25.71875 L 29.71875 7.71875 Z"></path></svg></div>
      <div style="padding-left:2px;padding-right:2px;padding-top:2px;padding-bottom:4px;margin-top:2px;background:#FAFAFA;width:100%;overflow-x:scroll;">
        <code style="background-color:#FAFAFA;padding-left:0;">stop_if_not(nrow(small_table) &gt; 10)</code>
      </div>
    </div>
  </div>
</div><div class="panel panel-danger">
  <div class="panel-heading" style="color:#333;border-color:transparent;">
    <div style="display:inline-flex;width:100%;">
      <div style="margin-top:2px;padding-left:5px;background:#FAFAFA;"><svg height="1.5em" viewBox="0 0 32 32" style="margin-top: 3px; fill: red;"><path d="M 16 3 C 8.832031 3 3 8.832031 3 16 C 3 23.167969 8.832031 29 16 29 C 23.167969 29 29 23.167969 29 16 C 29 8.832031 23.167969 3 16 3 Z M 16 5 C 22.085938 5 27 9.914063 27 16 C 27 22.085938 22.085938 27 16 27 C 9.914063 27 5 22.085938 5 16 C 5 9.914063 9.914063 5 16 5 Z M 12.21875 10.78125 L 10.78125 12.21875 L 14.5625 16 L 10.78125 19.78125 L 12.21875 21.21875 L 16 17.4375 L 19.78125 21.21875 L 21.21875 19.78125 L 17.4375 16 L 21.21875 12.21875 L 19.78125 10.78125 L 16 14.5625 Z"/></svg></div>
      <div style="padding-left:2px;padding-right:2px;padding-top:2px;padding-bottom:4px;margin-top:2px;background:#FAFAFA;width:100%;overflow-x:scroll;">
        <code style="background-color:#FAFAFA;padding-left:0;">stop_if_not("time" %in% colnames(small_table))</code>
      </div>
    </div>
    <hr style="margin-top:10px;margin-bottom:0;border:1px solid #EBCCD1;"/>
    <div class="panel-body" style="padding-left:13px;padding-top:15px;padding-right:13px;padding-bottom:15px;background:#FAFAFA;width:100%;overflow-x:scroll;">
      <code style="background-color:#FAFAFA;padding-left:0;overflow-x:scroll;">## Error: '"time" %in% colnames(small_table)' is not TRUE.</code>
    </div>
    <hr style="margin-top:0;margin-bottom:0;border:1px solid #EBCCD1;"/>
  </div>
</div>
    </div>
  </div>
</div>
<!--/html_preserve-->

Note that with multiple **pointblank** step functions chained together, only the first error encountered will be reported.

<!--html_preserve-->
<div class="pointblank-badge-container-inner" style="text-align: center; padding-bottom: 12px; font-size: 16px;">
  <span class="pointblank-badge label label-danger" data-toggle="collapse" data-target="#chunk-6791247" aria-expanded="false" aria-controls="chunk-6791247" style="cursor: pointer;">1 validation failed.</span>
</div>
<div id="chunk-6791247" class="pointblank-chunk panel panel-danger collapse" >
  <div class="panel" style="margin-bottom: 0px;">
    <div class="panel-body" style="padding-left: 18px; padding-top: 18px; padding-right: 18px; padding-bottom: 0px; background: #FAFAFA;">
      <div class="panel panel-danger">
  <div class="panel-heading" style="color:#333;border-color:transparent;">
    <div style="display:inline-flex;width:100%;">
      <div style="margin-top:2px;padding-left:5px;background:#FAFAFA;"><svg height="1.5em" viewBox="0 0 32 32" style="margin-top: 3px; fill: red;"><path d="M 16 3 C 8.832031 3 3 8.832031 3 16 C 3 23.167969 8.832031 29 16 29 C 23.167969 29 29 23.167969 29 16 C 29 8.832031 23.167969 3 16 3 Z M 16 5 C 22.085938 5 27 9.914063 27 16 C 27 22.085938 22.085938 27 16 27 C 9.914063 27 5 22.085938 5 16 C 5 9.914063 9.914063 5 16 5 Z M 12.21875 10.78125 L 10.78125 12.21875 L 14.5625 16 L 10.78125 19.78125 L 12.21875 21.21875 L 16 17.4375 L 19.78125 21.21875 L 21.21875 19.78125 L 17.4375 16 L 21.21875 12.21875 L 19.78125 10.78125 L 16 14.5625 Z"/></svg></div>
      <div style="padding-left:2px;padding-right:2px;padding-top:2px;padding-bottom:4px;margin-top:2px;background:#FAFAFA;width:100%;overflow-x:scroll;">
        <code style="background-color:#FAFAFA;padding-left:0;">small_table %&gt;% 
  col_exists(columns = vars(a, b, c, d, e, f)) %&gt;% # this passes validation
  rows_distinct() %&gt;%                              # this step fails (we see an error message)
  col_vals_gt(vars(d), 5000)                       # this also fails (we do not see its error)</code>
      </div>
    </div>
    <hr style="margin-top:10px;margin-bottom:0;border:1px solid #EBCCD1;"/>
    <div class="panel-body" style="padding-left:13px;padding-top:15px;padding-right:13px;padding-bottom:15px;background:#FAFAFA;width:100%;overflow-x:scroll;">
      <code style="background-color:#FAFAFA;padding-left:0;overflow-x:scroll;">## Error: Exceedance of failed test units where there weren't distinct rows across all columns.
## The `rows_distinct()` validation failed beyond the absolute threshold level (1).
## * failure level (2) &gt;= failure threshold (1)</code>
    </div>
    <hr style="margin-top:0;margin-bottom:0;border:1px solid #EBCCD1;"/>
  </div>
</div>
    </div>
  </div>
</div>
<!--/html_preserve-->

If all validations in a `validate` chunk do not fail, we can still inspect the validation code.

<!--html_preserve-->
<div class="pointblank-badge-container-inner" style="text-align: center; padding-bottom: 12px; font-size: 16px;">
  <span class="pointblank-badge label label-success" data-toggle="collapse" data-target="#chunk-3033339" aria-expanded="false" aria-controls="chunk-3033339" style="cursor: pointer;">All validations passed.</span>
</div>
<div id="chunk-3033339" class="pointblank-chunk panel panel-success collapse" >
  <div class="panel" style="margin-bottom: 0px;">
    <div class="panel-body" style="padding-left: 18px; padding-top: 18px; padding-right: 18px; padding-bottom: 0px; background: #FAFAFA;">
      <div class="panel panel-success">
  <div class="panel-heading" style="color:#333;border-color:transparent;">
    <div style="display:inline-flex;width:100%;">
      <div style="margin-top:2px;padding-left:5px;background:#FAFAFA;"><svg height="1.5em" viewBox="0 0 32 32" style="margin-top: 1px; fill: green;"><path d="M 28.28125 6.28125 L 11 23.5625 L 3.71875 16.28125 L 2.28125 17.71875 L 10.28125 25.71875 L 11 26.40625 L 11.71875 25.71875 L 29.71875 7.71875 Z"></path></svg></div>
      <div style="padding-left:2px;padding-right:2px;padding-top:2px;padding-bottom:4px;margin-top:2px;background:#FAFAFA;width:100%;overflow-x:scroll;">
        <code style="background-color:#FAFAFA;padding-left:0;">small_table %&gt;% 
  col_is_date("date") %&gt;%
  col_vals_gt(vars(d), vars(c), na_pass = TRUE)</code>
      </div>
    </div>
  </div>
</div>
    </div>
  </div>
</div>
<!--/html_preserve-->

We can provide a single, agent-based interrogation inside of a `validate` chunk (the reporting is visible once the `Agent Report` button is pressed). For best rendering results, don't place anything else inside the chunk. This acts as standalone reporting and will not result in document-level errors or warnings.

<!--html_preserve-->
<div class="pointblank-badge-container-inner" style="text-align: center; padding-bottom: 12px; font-size: 16px;">
  <span class="pointblank-badge label label-success" data-toggle="collapse" data-target="#chunk-1624130" aria-expanded="false" aria-controls="chunk-1624130" style="cursor: pointer;">All validations passed.</span>
</div>
<div id="chunk-1624130" class="pointblank-chunk panel panel-success collapse" >
  <div class="panel" style="margin-bottom: 0px;">
    <div class="panel-body" style="padding-left: 18px; padding-top: 18px; padding-right: 18px; padding-bottom: 0px; background: #FAFAFA;">
      <div class="panel panel-success">
  <div class="panel-heading" style="color:#333;border-color:transparent;">
    <div style="display:inline-flex;width:100%;">
      <div style="margin-top:2px;padding-left:5px;background:#FAFAFA;"><svg height="1.5em" viewBox="0 0 32 32" style="margin-top: 1px; fill: green;"><path d="M 28.28125 6.28125 L 11 23.5625 L 3.71875 16.28125 L 2.28125 17.71875 L 10.28125 25.71875 L 11 26.40625 L 11.71875 25.71875 L 29.71875 7.71875 Z"></path></svg></div>
      <div style="padding-left:2px;padding-right:2px;padding-top:2px;padding-bottom:4px;margin-top:2px;background:#FAFAFA;width:100%;overflow-x:scroll;">
        <code style="background-color:#FAFAFA;padding-left:0;">small_table %&gt;%
  create_agent() %&gt;%
  col_vals_gt(vars(a), 3) %&gt;%
  col_vals_expr(~ case_when(
    c &gt; 5 ~ a &gt; 5 &amp; d &gt;= 2000
  )) %&gt;%
  interrogate()</code>
      </div>
    </div>
  </div>
</div>
    </div>
  </div>
</div>
<!--/html_preserve-->
