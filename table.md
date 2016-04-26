
| Data source | Property | Connection String Format | Notes
| ----------- | --------------------- | ---------------- | ------------- |
| DB2 | `dsn` | `DATABASE=<database>;HOSTNAME=<host>;PORT=<port>;PROTOCOL=TCPIP;UID=<uid>;PWD=<pwd>` | |
| Cloudant| `url` | `https://<username>:<password>@<host>` | `url` does not override the field `database`. You still must  provide it. |
| Mongodb|  `url` | `mongodb://<username>:<password>@<host>:<port>/<database>`  | Note: Credentials are converted to a `url` to initiate connection. |
| MySQL | `url` | `mysql://<username>:<password>@<host>/<database>?<option_name>=<opt_value>` | See [MySQL url format](https://github.com/felixge/node-mysql#connection-options) for details. |
| PostgreSQL | `url` |  `postgres://<username>:<password>@<host>/<database>`  | See [PostgreSQL url format](https://github.com/brianc/node-postgres#client-pooling) for details. |
| MSSQL| `url` | `mssql://<username>:<password>@<host>:<port>/<database>?<option_name>=<opt_value>` | See [MsSQL url format](https://github.com/patriksimek/node-mssql#formats) for details. |
| Oracle | `tns` |  `DESCRIPTION=(ADDRESS=(PROTOCOL=TCP)(HOST=<host>)(PORT=<port>))(CONNECT_DATA=(SERVER=DEDICATED)(SERVICE_NAME=<database>))`  | You must also provide `tns`, `user` and `password`. See [Oracle connection using tns](https://github.com/joeferner/node-oracle#alternative-connection-using-tns) for details. |

