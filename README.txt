ZooKeeper quorum tool.

Usage:
    $0 [<ID>:]<IP> [[<ID>:]<IP> ... ]

    Creates a list of serviced variables to set up a ZooKeeper ensemble.
    Run the same command on each machine, and this script will output a script
    to set the values SERVICED_ISVCS_ZOOKEEPER_ID, SERVICED_ZK,
    SERVICED_ISVCS_ZOOKEEPER_QUORUM, and SERVICED_ISVCS_START on each host's
    /etc/default/serviced file.

Examples:
    ./zookeeper-quorum-tool 19.103.3.{240,216,233}

    ./zookeeper-quorum-tool 1:19.103.3.240 2:19.103.3.216 3:19.103.3.233

    These two examples are equivalent. In either case, they should only generate
    output to stdout, so you won't get anything out of this until you append the
    output to /etc/default/serviced and restart the service.
