
Create and index: 
```sql
-- list all indexes on all tables:
\di
-- default name
CREATE INDEX ON offers (user_id);
-- explicit name 
CREATE INDEX offers_user_id_idx ON offers (user_id);
-- if not exists requires name
CREATE INDEX IF NOT EXISTS offers_user_id_idx ON offers (user_id);
-- concurrently
CREATE INDEX CONCURRENTLY offers_user_id_idx ON offers (user_id);
```

- Can take a long time, writes are blocked until index is built
- Use concurrently if need write access but it will take longer and use more resources
- May need to run ANALYZE command to update stats so query planner can make educated decisions