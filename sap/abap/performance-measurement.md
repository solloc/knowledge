# Performance measurement

```text
cl_abap_trace_switch=>on(
  EXPORTING
    p_prog              = sy-repid    " Program To Be Measured
).
```

```text
SET RUN TIME ANALYZER ON.
```

```text
SET RUN TIME ANALYZER OFF.
```

```text
cl_abap_trace_switch=>off( ).
```

Analyze with [Runtime analysis](../transaction-code/runtime-analysis.md)

