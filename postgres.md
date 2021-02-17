# PostgreSQL  

## CLI Utils
* `psql` Lets you carry out admin functions without needing to now SQL commands
    * log in with postgres user `psql postgres`
    * exit `\q + enter`
    * `\du` list users 
    * `\?` and `\help` help prompts
    * Backup `pg_dump -a -n public URL`
    * Restore `psql URL -f /path/to/file`
