# Delete table row within loop

```text
DATA lt_draw TYPE TABLE OF draw.
DATA ls_draw TYPE draw.

LOOP AT lt_draw INTO ls_draw.
  DELETE lt_draw USING KEY loop_key.
ENDLOOP.
```

