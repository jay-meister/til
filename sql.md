Update with case:
```sql
UPDATE offers o
  SET create_flow = CASE
    WHEN o."is_revision?" = true THEN 'END_REVISE'
    WHEN o."is_revision?" = false AND o.original_offer_id IS NOT NULL THEN 'VOID_REPLACE'
    ELSE 'NEW'
  END
  WHERE ... ;
```

Update from statement:
```sql
update offers o
set box_rental_budget_code = cf.value
from custom_fields cf
where cf.name = 'Budget code box' and cf.offer_id = o.id
;
```

Update string field:
```sql
UPDATE offers SET mobile_number = CONCAT('+44', mobile_number) WHERE id = 101;
```

Enum types:
```sql
--create type
CREATE TYPE offer_create_flow AS ENUM ('NEW', 'COPY', 'END_REVISE', 'VOID_REPLACE', 'CSV');
--cast string as type
UPDATE offers SET create_flow = 'NEW'::offer_create_flow;
--DROP TYPE IF EXISTS offer_create_flow;
```

JSONB types:
```sql
--select & where clause
select ot ->> 'additional_day_penalty' from timecard_data where ot ->> 'additional_day_penalty' in ('6th', '7th');
--update jsonb field
update timecard_data set ot = jsonb_set(ot, '{bta}', '60') where id = 4816;
update timecard_data set ot = jsonb_set(ot, '{bta}', 'null') where id = 4816;
```

```sql
-- Add not null constraint to column
ALTER TABLE tasks ALTER COLUMN action SET NOT NULL;
-- remove not null constraint
ALTER TABLE tasks ALTER COLUMN action DROP NOT NULL;
```
