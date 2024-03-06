---
title: "Konfiguration"
linkTitle: "Konfiguration"
type: "docs"
---

Die in der Tabelle aufgeführten Parameter stellen die spezifischen Konfigurationseinstellungen dar, die wir an die MariaDB-Standardkonfiguration anpassen. Diese Parameter sind auf die Anforderungen unserer Plattform zugeschnitten und werden sorgfältig ausgewählt, um Leistung und Zuverlässigkeit zu optimieren.

> **Hinweis:** Die mit einem Sternchen (*) gekennzeichneten Parameter werden dynamisch auf Grundlage der verfügbaren Rechenressourcen berechnet, um eine nahtlose vertikale Skalierung zu ermöglichen.

| **Parameter**                       | **Type** | **Default**                                                                                               | **Modifiable** | **Restart Required** | **Min** | **Max**             | **Allowed Values**                                                                                                                                                                                                                                                                                                                                                   |
|-------------------------------------|----------|-----------------------------------------------------------------------------------------------------------|----------------|---------------------|---------|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| binlog_cache_size                   | integer  | 32768                                                                                                     | True           | False               | 4096    | 18446744073709548000|                                                                                                                                                                                                                                                                                                                                                                      |
| binlog_expire_logs_auto_purge       | string   | ON                                                                                                        | False          | False               |         |                     | OFF<br>ON                                                                                                                                                                                                                                                                                                                                                           |
| binlog_expire_logs_seconds          | integer  | 86400                                                                                                     | False          | False               | 0       | 4294967295          |                                                                                                                                                                                                                                                                                                                                                                      |
| binlog_format                       | string   | ROW                                                                                                       | False          | False               |         |                     | ROW<br>MIXED<br>STATEMENT                                                                                                                                                                                                                                                                                                                                           |
| binlog_gtid_simple_recovery         | string   | ON                                                                                                        | False          | True                |         |                     | OFF<br>ON                                                                                                                                                                                                                                                                                                                                                           |
| connect_timeout                     | integer  | 10                                                                                                        | True           | False               |         |                     |                                                                                                                                                                                                                                                                                                                                                                      |
| enforce_gtid_consistency            | string   | ON                                                                                                        | False          | False               |         |                     | OFF<br>ON<br>WARN                                                                                                                                                                                                                                                                                                                                                    |
| gtid_mode                           | string   | ON                                                                                                        | False          | False               |         |                     | OFF<br>OFF_PERMISSIVE<br>ON_PERMISSIVE<br>ON                                                                                                                                                                                                                                                                                                                           |
| innodb_buffer_pool_size*            | integer  | 134217728                                                                                                 | True           | False               | 2097152 | 9223372036854776000 |                                                                                                                                                                                                                                                                                                                                                                      |
| innodb_file_per_table               | string   | ON                                                                                                        | False          | False               |         |                     | ON<br>OFF                                                                                                                                                                                                                                                                                                                                                           |
| innodb_flush_method                 | string   | O_DIRECT                                                                                                  | False          | True                |         |                     | fsync<br>O_DSYNC<br>littlesync<br>nosync<br>O_DIRECT<br>O_DIRECT_NO_FSYNC                                                                                                                                                                                                                                                                                            |
| innodb_lock_wait_timeout            | integer  | 50                                                                                                        | True           | False               | 0       | 100000000           |                                                                                                                                                                                                                                                                                                                                                                      |
| innodb_log_buffer_size              | integer  | 16777216                                                                                                  | True           | True                | 262144  | 4294967295          |                                                                                                                                                                                                                                                                                                                                                                      |
| innodb_redo_log_capacity*           | integer  | 104857600                                                                                                 | True           | False               | 8388608 | 137438953472        |                                                                                                                                                                                                                                                                                                                                                                      |
| innodb_strict_mode                  | string   | ON                                                                                                        | True           | False               |         |                     | ON<br>OFF                                                                                                                                                                                                                                                                                                                                                           |
| key_buffer_size*                    | integer  | 134217728                                                                                                 | True           | False               | 8       |                     |                                                                                                                                                                                                                                                                                                                                                                      |
| local_infile                        | string   | OFF                                                                                                       | False          | False               |         |                     | ON<br>OFF                                                                                                                                                                                                                                                                                                                                                           |
| lock_wait_timeout                   | integer  | 31536000                                                                                                  | True           | False               | 1       | 31536000            |                                                                                                                                                                                                                                                                                                                                                                      |
| log_bin_trust_function_creators     | string   | OFF                                                                                                       | True           | False               |         |                     | ON<br>OFF                                                                                                                                                                                                                                                                                                                                                           |
| max_allowed_packet*                 | integer  | 16777216                                                                                                  | False          | False               | 1024    | 1073741824          |                                                                                                                                                                                                                                                                                                                                                                      |
| max_binlog_size                     | integer  | 1073741824                                                                                                | True           | False               | 4096    | 1073741824          |                                                                                                                                                                                                                                                                                                                                                                      |
| max_connect_errors                  | integer  | 100                                                                                                       | True           | False               | 1       | 4294967295          |                                                                                                                                                                                                                                                                                                                                                                      |
| max_connections*                    | integer  | 151                                                                                                       | True           | True                | 10      | 100000              |                                                                                                                                                                                                                                                                                                                                                                      |
| open_files_limit                    | integer  | 5000                                                                                                      | True           | True                | 0       | 4294967295          |                                                                                                                                                                                                                                                                                                                                                                      |
| require_secure_transport            | string   | ON                                                                                                        | False          | False               |         |                     | ON<br>OFF                                                                                                                                                                                                                                                                                                                                                           |
| skip_name_resolve                   | string   | ON                                                                                                        | False          | True                |         |                     | ON<br>OFF                                                                                                                                                                                                                                                                                                                                                           |
| ssl_cipher                          | string   | ECDHE-ECDSA-AES128-GCM-SHA256:<br>ECDHE-RSA-AES128-GCM-SHA256:<br>ECDHE-ECDSA-AES256-GCM-SHA384:<br>ECDHE-RSA-AES256-GCM-SHA384:<br>ECDHE-ECDSA-CHACHA20-POLY1305:<br>ECDHE-RSA-CHACHA20-POLY1305:<br>DHE-RSA-AES128-GCM-SHA256:<br>DHE-RSA-AES256-GCM-SHA384 | True           | True                |         |                     |                                                                                                                                                                                                                                                                                                                                                                      |
| sql_mode                           | string   | ONLY_FULL_GROUP_BY<br>STRICT_TRANS_TABLES<br>NO_ZERO_IN_DATE<br>NO_ZERO_DATE<br>ERROR_FOR_DIVISION_BY_ZERO<br>NO_ENGINE_SUBSTITUTION | True           | False               |         |                     | ALLOW_INVALID_DATES<br>ANSI<br>ANSI_QUOTES<br>ERROR_FOR_DIVISION_BY_ZERO<br>HIGH_NOT_PRECEDENCE<br>IGNORE_SPACE<br>NO_AUTO_VALUE_ON_ZERO<br>NO_BACKSLASH_ESCAPES<br>NO_DIR_IN_CREATE<br>NO_ENGINE_SUBSTITUTION<br>NO_UNSIGNED_SUBTRACTION<br>NO_ZERO_DATE<br>NO_ZERO_IN_DATE<br>ONLY_FULL_GROUP_BY<br>PAD_CHAR_TO_FULL_LENGTH<br>PIPES_AS_CONCAT<br>REAL_AS_FLOAT<br>STRICT_ALL_TABLES<br>STRICT_TRANS_TABLES<br>TIME_TRUNCATE_FRACTIONAL |
| table_open_cache*                  | integer  | 2000                                                                                                      | True           | True                | 1       | 1048576             |                                                                                                                                                                                                                                                                                                                                                                      |
| tls_version                        | string   | TLSv1.2<br>TLSv1.3                                                                                        | True           | True                |         |                     |                                                                                                                                                                                                                                                                                                                                                                      |

### Erläuterung der Tabelle

- **Parameter:** In dieser Spalte werden die Konfigurationsparameter aufgeführt.
- **Type:** Gibt den Datentyp des Konfigurationsparameters an (z. B. Integer, String).
- **Default:** Zeigt den Standardwert für jeden Parameter an.
- Modifiable:** Zeigt an, ob der Parameter modifiziert werden kann (`true`/`false`).
- **Restart Required:** Gibt an, ob ein Neustart des Servers erforderlich ist, damit Änderungen wirksam werden (`true`/`false`).
- **Min:** Zeigt den minimal zulässigen Wert für numerische Parameter an.
- **Max:** Zeigt den maximal zulässigen Wert für numerische Parameter an.
- **Allowed Values:** Zeigt die zulässigen Werte für String-Parameter an.

<br>

**Wenn Sie Ihre DBaas-Konfiguration anpassen müssen oder einen nicht aufgeführten Parameter ändern müssen, wenden Sie sich bitte an unser Support-Team [eröffnen Sie ein Ticket](https://customerservice.plusserver.com/support/ticket-create).**

<br>

>*Wir arbeiten an einer Funktion, mit der Sie Ihre DBaaS-Einstellungen direkt in unserem Kundenportal ändern können. Bis dahin danken wir Ihnen für Ihre Geduld, während wir unsere Dienste verbessern.*