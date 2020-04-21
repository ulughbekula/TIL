Convert CSV to SQLite
1. sqlite3 db_to_create.db
2. .mode csv
3. .import CSV_to_import.csv db_to_create
4. Check if it worked: sqlite> .schema db_to_create

Source: https://levlaz.org/converting-csv-to-a-sqlite-database/
