check-unused-keys is a Perl script to identify unused indexes (and tables), based on the INFORMATION\_SCHEMA.INDEX\_STATISTICS Percona patch. With the --create-alter option, it will create full ALTER TABLE statements to drop the unused indexes.

## Usage ##
```
%> ./check_unused_keys --help
Usage:
     check-unused-keys [OPTIONS]

     Options:
       -d, --databases=<dbname>  Comma-separated list of databases to check
       -h, --help                Display this message and exit
       -H, --hostname=<hostname> The target MySQL server host
       --[no]create-alter        Print ALTER statements for each table
       --ignore-databases        Comma-separated list of databases to ignore
       --ignore-indexes          Comma-separated list of indexes to ignore
                                     db_name.tbl_name.index_name
       --ignore-tables           Comma-separated list of tables to ignore
                                     db_name.tbl_name
       --[no]ignore-primary      Whether or not to ignore PRIMARY KEY
       --[no]ignore-unique       Whether or not to ignore UNIQUE indexes
       --options-file            The options file to use
       --[no]print-unused-tables 
                                 Whether or not to print a list of unused tables
                                     (indexes from unused tables are never shown)
       -p, --password=<password> The password of the MySQL user
       -i, --port=<portnum>      The port MySQL is listening on
       -s, --socket=<sockfile>   Use the specified mysql unix socket to connect
       -t, --tables=<tables>     Comma-separated list of tables to evaluate
                                     db_name.tbl_name
       --[no]summary             Display summary information
       -u, --username=<username> The MySQL user used to connect
       -v, --verbose             Increase verbosity level
       -V, --version             Display version information and exit

     Defaults are:

     ATTRIBUTE                  VALUE
     -------------------------- ------------------
     databases                  ALL databases 
     help                       FALSE
     hostname                   localhost
     create-alter               FALSE
     ignore-databases           No default value
     ignore-indexes             No default value
     ignore-primary             TRUE
     ignore-tables              No default value
     ignore-unique              TRUE
     options-file               ~/.my.cnf
     password                   No default value
     print-unused-tables        FALSE
     port                       3306
     socket                     No default value
     summary                    TRUE
     tables                     No Default Value
     username                   No default value
     verbose                    0 (out of 2)
     version                    FALSE
```