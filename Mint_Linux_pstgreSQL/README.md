# ```psql -U postgres``` 리눅스에서 에러나서 ```sudo -i -u postgres```로 들어감

```bash
psql -U postgres                                                           
psql: error: connection to server on socket "/var/run/postgresql/.s.PGSQL.5432" failed: FATAL:  Peer authentication failed for user "postgres"

 ~ ····························································· at 15:13:43 
sudo -i -u postgres                                                        ─╯
postgres@gy-MS-7D42:~$ psql
psql (14.8 (Ubuntu 14.8-0ubuntu0.22.04.1))
Type "help" for help.

postgres=# \l
postgres=# \q
postgres@gy-MS-7D42:~$ exit
logout


```

https://stackoverflow.com/questions/69676009/psql-error-connection-to-server-on-socket-var-run-postgresql-s-pgsql-5432

# postgresql_gy

- postgre 명령어 정리
```
\l   list 확인
\q   quit 종료
```

https://www.devkuma.com/docs/postgresql/%EC%8A%A4%ED%82%A4%EB%A7%88-schema/

# Linux (Mint Linux install)

```bash
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get -y install postgresql
```


https://www.postgresql.org/download/linux/debian/

<hr>

<hr>

