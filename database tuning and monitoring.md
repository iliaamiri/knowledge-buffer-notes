
## MSSQL
```sql
-- Total open connections 
SELECT COUNT(*) AS OpenConnections
FROM sys.dm_exec_connections;

-- List of all the open connections and the processes that are using it (with their name and IP address, etc.)
SELECT
    c.session_id,
    s.login_name,
    c.client_net_address,
    s.host_name,
    s.program_name,
    c.connect_time
FROM sys.dm_exec_connections c
         JOIN sys.dm_exec_sessions s
              ON c.session_id = s.session_id;

-- List of all the open connections along with their max Idle time
SELECT
    c.session_id,
    s.login_name,
    c.client_net_address,
    s.host_name,
    s.program_name,
    c.connect_time
FROM sys.dm_exec_connections c
         JOIN sys.dm_exec_sessions s
              ON c.session_id = s.session_id;

-- Top 10 of the most used queries and their speed and everything
SELECT TOP 10
    qs.total_elapsed_time / qs.execution_count AS avg_time,
    qs.execution_count,
    qs.total_elapsed_time,
    qs.total_worker_time,
    qs.total_logical_reads,
    qs.total_physical_reads,
    qs.total_logical_writes,
    q.text
FROM sys.dm_exec_query_stats qs
         CROSS APPLY sys.dm_exec_sql_text(qs.sql_handle) q
ORDER BY avg_time DESC;


```