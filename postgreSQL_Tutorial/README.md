# Learn PostgreSQL Tutorial - Full Course for Beginners

https://youtu.be/qw--VYLpxG4


# Learn Database Administration - PostgreSQL Database Administration (DBA) for Beginners

https://youtu.be/aUfPf-clLLs

<hr>

# SQL For Web Developers - Complete Database Course | freeCodeCamp.org

https://youtu.be/KBDSJU3cGkc?si=in2DZFuVPuoCkrLi

# SQL Tutorial Videos🔥[2022 Updated]

https://youtube.com/playlist?list=PLEiEAq2VkUUKL3yPbn8yWnatjUg0P0I-Z



# Learn SQL In 60 Minutes

https://youtu.be/p3qvj9hO_Bo?si=UaCUFlXNGmYVrbZ-

# PostgreSQL 기본 명령어

- local에서 실행
  - https://stackoverflow.com/questions/31645550/postgresql-why-psql-cant-connect-to-server

```bash

$ sudo gpasswd -a postgres ssl-cert
Adding user postgres to group ssl-cert


$ sudo chown root:ssl-cert  /etc/ssl/private/ssl-cert-snakeoil.key


$ sudo chmod 740 /etc/ssl/private/ssl-cert-snakeoil.key


$ sudo service postgresql restart
 * Restarting PostgreSQL 16 database server                                                                                                    [ OK ]


$ psql
psql: error: connection to server on socket "/var/run/postgresql/.s.PGSQL.5432" failed: FATAL:  role "y" does not exist


$ sudo systemctl status postgresql
System has not been booted with systemd as init system (PID 1). Can't operate.
Failed to connect to bus: Host is down


$ pg_lsclusters
Ver Cluster Port Status Owner    Data directory              Log file
16  main    5432 online postgres /var/lib/postgresql/16/main /var/log/postgresql/postgresql-16-main.log


$ sudo pg_ctlcluster 16 main start
Cluster is already running.


$ sudo service postgresql start
 * Starting PostgreSQL 16 database server                                                                                                      [ OK ]

$ sudo su - postgres
Welcome to Ubuntu 24.04.4 LTS (GNU/Linux 4.4.0-18362-Microsoft x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information as of Fri Feb 13 12:41:45 KST 2026

  System load:  0.52                Processes:             18
  Usage of /:   67.1% of 237.84GB   Users logged in:       0
  Memory usage: 85%                 IPv4 address for eth1: 192.168.219.72
  Swap usage:   12%

This message is shown once a day. To disable it please create the
/var/lib/postgresql/.hushlogin file.
postgres@DESKTOP-7FCSUVF:~$ psql
psql (16.11 (Ubuntu 16.11-0ubuntu0.24.04.1))
Type "help" for help.
```

# postgres서버 잘 돌아가는지(status) 확인

```bash
$ sudo service postgresql status
16/main (port 5432): online


$ sudo su - postgres

# 2번 더 들어가야함. docker 같은 기분
postgres@DESKTOP-7FCSUVF:~$ /l
-bash: /l: No such file or directory

# psql 진입
postgres@DESKTOP-7FCSUVF:~$ psql
```

# postgres비번 설정
- https://stackoverflow.com/questions/27107557/what-is-the-default-password-for-postgres

```bash
user:~$ sudo -i -u postgres
postgres@user:~$ psql
```

- Execute this query in postgres shell:

```bash
postgres=# ALTER USER postgres PASSWORD 'mynewpassword';
```

- 비번 설정한거 잘됨.
```bash
postgres@DESKTOP-7FCSUVF:~$ psql -h localhost -p 5432 -U postgres -d postgres
```

- [영상  Postgres는 데이터베이스가 아닙니다. | DevOps Toolbox](https://youtu.be/b7eXdUOzUTM?si=UOCYuVzgPzkLjTN7)
