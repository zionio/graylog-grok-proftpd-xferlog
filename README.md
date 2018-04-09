ProFTPD Xferlog GROK pattern for Graylog
========================================

Pattern
-------

    "name":"PROFTPDXFER_TIMESTAMP"
    "pattern":"%{DAY} %{MONTH} %{MONTHDAY} %{HOUR}:%{MINUTE}:%{SECOND} %{YEAR}"
	"name":"PROFTPD_XFERLOG",
	"pattern":"%{PROFTPDXFER_TIMESTAMP:proftpd_xfer_timestamp} %{DATA:proftpd_xfer_transfer-time:int} %{HOSTNAME:proftpd_xfer_remote-host} %{INT:proftpd_xfer_file-size} %{UNIXPATH:proftpd_xfer_filename} %{WORD:proftpd_xfer_transfer-type} %{WORD:proftpd_xfer_action-flag} %{WORD:proftpd_xfer_direction} %{WORD:proftpd_xfer_access-mode} %{USERNAME:proftpd_xfer_username} %{WORD:proftpd_xfer_service-name} %{INT:proftpd_xfer_auth-method} %{DATA:proftpd_xfer_auth-userid} %{WORD:proftpd_xfer_completion-status}"

Example message
---------------

	Mon Apr 09 10:18:33 2018 5 101.102.103.104 133974969 /path/to/file.zip b _ i r user1 ftps 0 * c

Fields
------

    proftpd_xfer_access-mode: r
    proftpd_xfer_action-flag: _
    proftpd_xfer_auth-method: 0
    proftpd_xfer_auth-userid: *
    proftpd_xfer_completion-status: c
    proftpd_xfer_direction: i
    proftpd_xfer_file-size: 133974969
    proftpd_xfer_filename: /path/to/file.zip
    proftpd_xfer_remote-host: 101.102.103.104
    proftpd_xfer_service-name: ftps
    proftpd_xfer_timestamp: Mon Apr 09 10:18:33 2018
    proftpd_xfer_transfer-time: 5
    proftpd_xfer_transfer-type: b
    proftpd_xfer_username: user1


Installation
------------

Go to **Graylog Web Interface** -> **System** -> **Content Packs** then select *content_pack.json* file and upload it.

[![screen1](https://i.imgbox.com/HAsDC4FR.png)](https://i.imgbox.com/wP2n4HXH.png)