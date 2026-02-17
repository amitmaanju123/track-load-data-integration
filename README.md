# track-load-data-integration
Talend ETL pipeline for incremental data load with deduplication and insert/update (upsert) logic using tMap and lookup.
This project implements an ETL pipeline in Talend for loading and maintaining data in the `track_load` table.

## The pipeline performs
- Data extraction from source table
- Logging
- Column filtering
- Duplicate removal
- Lookup comparison
- Conditional Insert and Update operations

## ETL Workflow

1. Pre-check execution using tJava
2. Read data from source (track_load)
3. Log data (tLogRow)
4. Filter required columns (tFilterColumns)
5. Remove duplicates (tUniqRow)
6. Lookup existing records from target table
7. Perform transformation using tMap
8. Route records to:
   - Insert (new records)
   - Update (existing records)
9. Load data into target table
    
## Talend Components Used

- tJava
- tDBInput (track_load)
- tLogRow
- tFilterColumns
- tUniqRow
- tMap
- tDBOutput (Insert)
- tDBOutput (Update)
