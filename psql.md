### Database dumps

duplicate a local database:
```bash
pg_dump ev2_dev | psql ev2_delete
```

dump remote db to local
```bash
--pg_dump -U remote_user -h remote_server -t table_to_copy source_db | psql target_db
pg_dump -U remote_user -h remote_server -t table_to_copy --create db_name | psql 
```

dump startpacks table data to a local file in `insert` format:
```bash
pg_dump <full_db_url_here> --table=startpacks --data-only --column-inserts > startpack_data.dump
```

**Rename database**
```bash
psql -c 'ALTER DATABASE "ev2_dev" RENAME TO "ev2_dev_keep"'
```
