# OpenSQL existence check

```text
select 1 from draw
  into table @data(lt_exists_limit)
  up to 1 rows
  where dokar = @p_dokar.

  if lines( lt_exists_limit ) > 0.
    write 'at least one record exists'.
  endif.
```

