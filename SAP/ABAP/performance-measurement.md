# Performance measurement

``` ABAP
cl_abap_trace_switch=>on(
  EXPORTING
    p_prog              = sy-repid    " Program To Be Measured
).
```
``` ABAP
SET RUN TIME ANALYZER ON.
```
``` ABAP
SET RUN TIME ANALYZER OFF.
```
``` ABAP
cl_abap_trace_switch=>off( ).
```

Analyze with [Runtime analysis](/SAP/transaction-code/runtime-analysis.md)