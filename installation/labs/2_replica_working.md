### Used ansible to setup mysql and show the replica status

```
ansible-playbook slave-status.yml 

PLAY [tag_mysql_slave] ***********************************************************************************************************************************************************************************************************************

TASK [capture slave replication status output] ***********************************************************************************************************************************************************************************************
changed: [34.253.155.59]

TASK [debug] *********************************************************************************************************************************************************************************************************************************
ok: [34.253.155.59] => {
    "slave_status": {
        "changed": true, 
        "cmd": "mysql -e \"SHOW SLAVE STATUS \\G;\"", 
        "delta": "0:00:00.007464", 
        "end": "2017-06-05 17:30:17.302327", 
        "rc": 0, 
        "start": "2017-06-05 17:30:17.294863", 
        "stderr": "", 
        "stderr_lines": [], 
        "stdout": "*************************** 1. row ***************************\n               Slave_IO_State: Waiting for master to send event\n                  Master_Host: ip-172-31-5-114.eu-west-1.compute.internal\n                  Master_User: root\n                  Master_Port: 3306\n                Connect_Retry: 60\n              Master_Log_File: mysql_binary_log.000016\n          Read_Master_Log_Pos: 360\n               Relay_Log_File: mysqld-relay-bin.000002\n                Relay_Log_Pos: 290\n        Relay_Master_Log_File: mysql_binary_log.000016\n             Slave_IO_Running: Yes\n            Slave_SQL_Running: Yes\n              Replicate_Do_DB: \n          Replicate_Ignore_DB: \n           Replicate_Do_Table: \n       Replicate_Ignore_Table: \n      Replicate_Wild_Do_Table: \n  Replicate_Wild_Ignore_Table: \n                   Last_Errno: 0\n                   Last_Error: \n                 Skip_Counter: 0\n          Exec_Master_Log_Pos: 360\n              Relay_Log_Space: 464\n              Until_Condition: None\n               Until_Log_File: \n                Until_Log_Pos: 0\n           Master_SSL_Allowed: No\n           Master_SSL_CA_File: \n           Master_SSL_CA_Path: \n              Master_SSL_Cert: \n            Master_SSL_Cipher: \n               Master_SSL_Key: \n        Seconds_Behind_Master: 0\nMaster_SSL_Verify_Server_Cert: No\n                Last_IO_Errno: 0\n                Last_IO_Error: \n               Last_SQL_Errno: 0\n               Last_SQL_Error: \n  Replicate_Ignore_Server_Ids: \n             Master_Server_Id: 1\n                  Master_UUID: 2174a865-4a22-11e7-bb99-0a1c7cb027e4\n             Master_Info_File: /var/lib/mysql/master.info\n                    SQL_Delay: 0\n          SQL_Remaining_Delay: NULL\n      Slave_SQL_Running_State: Slave has read all relay log; waiting for the slave I/O thread to update it\n           Master_Retry_Count: 86400\n                  Master_Bind: \n      Last_IO_Error_Timestamp: \n     Last_SQL_Error_Timestamp: \n               Master_SSL_Crl: \n           Master_SSL_Crlpath: \n           Retrieved_Gtid_Set: \n            Executed_Gtid_Set: \n                Auto_Position: 0", 
        "stdout_lines": [
            "*************************** 1. row ***************************", 
            "               Slave_IO_State: Waiting for master to send event", 
            "                  Master_Host: ip-172-31-5-114.eu-west-1.compute.internal", 
            "                  Master_User: root", 
            "                  Master_Port: 3306", 
            "                Connect_Retry: 60", 
            "              Master_Log_File: mysql_binary_log.000016", 
            "          Read_Master_Log_Pos: 360", 
            "               Relay_Log_File: mysqld-relay-bin.000002", 
            "                Relay_Log_Pos: 290", 
            "        Relay_Master_Log_File: mysql_binary_log.000016", 
            "             Slave_IO_Running: Yes", 
            "            Slave_SQL_Running: Yes", 
            "              Replicate_Do_DB: ", 
            "          Replicate_Ignore_DB: ", 
            "           Replicate_Do_Table: ", 
            "       Replicate_Ignore_Table: ", 
            "      Replicate_Wild_Do_Table: ", 
            "  Replicate_Wild_Ignore_Table: ", 
            "                   Last_Errno: 0", 
            "                   Last_Error: ", 
            "                 Skip_Counter: 0", 
            "          Exec_Master_Log_Pos: 360", 
            "              Relay_Log_Space: 464", 
            "              Until_Condition: None", 
            "               Until_Log_File: ", 
            "                Until_Log_Pos: 0", 
            "           Master_SSL_Allowed: No", 
            "           Master_SSL_CA_File: ", 
            "           Master_SSL_CA_Path: ", 
            "              Master_SSL_Cert: ", 
            "            Master_SSL_Cipher: ", 
            "               Master_SSL_Key: ", 
            "        Seconds_Behind_Master: 0", 
            "Master_SSL_Verify_Server_Cert: No", 
            "                Last_IO_Errno: 0", 
            "                Last_IO_Error: ", 
            "               Last_SQL_Errno: 0", 
            "               Last_SQL_Error: ", 
            "  Replicate_Ignore_Server_Ids: ", 
            "             Master_Server_Id: 1", 
            "                  Master_UUID: 2174a865-4a22-11e7-bb99-0a1c7cb027e4", 
            "             Master_Info_File: /var/lib/mysql/master.info", 
            "                    SQL_Delay: 0", 
            "          SQL_Remaining_Delay: NULL", 
            "      Slave_SQL_Running_State: Slave has read all relay log; waiting for the slave I/O thread to update it", 
            "           Master_Retry_Count: 86400", 
            "                  Master_Bind: ", 
            "      Last_IO_Error_Timestamp: ", 
            "     Last_SQL_Error_Timestamp: ", 
            "               Master_SSL_Crl: ", 
            "           Master_SSL_Crlpath: ", 
            "           Retrieved_Gtid_Set: ", 
            "            Executed_Gtid_Set: ", 
            "                Auto_Position: 0"
        ]
    }
}

PLAY RECAP ***********************************************************************************************************************************************************************************************************************************
34.253.155.59              : ok=2    changed=1    unreachable=0    failed=0   

```

Needed a firewall change (added 3306 to the aws security group) to make things work.
