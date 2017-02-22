MongoDB
============
Ansible role which manage [MongoDB](http://www.mongodb.org/)

#### Variables

```yaml
mongodb_install_enabled: true
mongodb_install_major: 3
mongodb_install_minor: 4
mongodb_install_patch: "*"

mongodb_daemon_bin: /usr/bin/mongod
mongodb_daemon_serviceFile: /etc/systemd/system/mongod.service
mongodb_daemon_user: mongod
mongodb_daemon_group: mongod

mongodb_conf_file: /etc/mongodb/mongod.conf            # Configuration file path
mongodb_conf_pidFile: /var/run/mongodb/mongod.pid      # PID file path
mongodb_conf_logFile: /var/log/mongodb/mongod.log      # Log file path (not recommended to be changed)
mongodb_conf_keyFile: /etc/mongodb/mongod.key          # Keyfile path
mongodb_conf_dbPath: /var/lib/mongo                    # Directory for datafiles
mongodb_conf_dbEngine: wiredTiger                      # Storage Engine
mongodb_conf_auth: false                               # Client authentication
mongodb_conf_bindIp: "127.0.0.1"                       # Comma separated list of ip addresses to listen on
mongodb_conf_cpu: yes                                  # Periodically show cpu and iowait utilization
mongodb_conf_httpInterface: false                      # Enable (deprecated) http interface
mongodb_conf_ipv6: false                               # Enable IPv6 support
mongodb_conf_journal: true                             # Enable journaling
mongodb_conf_logAppend: true                           # Append to logpath instead of over-writing
mongodb_conf_maxConns: 800                             # Max number of simultaneous connections
mongodb_conf_port: 27017                               # Specify TCP port number
mongodb_conf_sysLog: false                             # Log to system's syslog facility instead of file (ignored if logpath set)
mongodb_conf_oplogSize: 1024
mongodb_conf_key: ""                                   # Keyfile content

mongodb_admin_user: "admin"
mongodb_admin_password: "adminPassword"

mongodb_replSet_enabled: false
mongodb_replSet_name: ""
mongodb_replSet_master: "127.0.0.1"
mongodb_replSet_isMaster: false

mongodb_shell_run: false
mongodb_shell_commands: {}                             # Define mongo shell commands to run
                                                       # Syntax: mongodb_shell:
                                                       #          dbname:
                                                       #           - db.setProfilingLevel(1, 50)

# Log rotation
mongodb_logRotate_enabled: true
mongodb_logRotate_file: /etc/logrotate.d/mongodb.conf
mongodb_logRotate_options:
  - compress
  - copytruncate
  - daily
  - dateext
  - rotate 7
  - size 10M

mongodb_safeMode: false
```
