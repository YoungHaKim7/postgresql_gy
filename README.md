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

<hr>

# macOS postgresql 실행

```
LC_ALL="C" /opt/homebrew/opt/postgresql@15/bin/postgres -D /opt/homebrew/var/postgresql@15

// or
brew services start postgresql@15

// list 확인
brew services list
```

- psql

```
/opt/homebrew/Cellar/postgresql@14/14.8_2/bin/psql
```

- /opt/homebrew/Cellar/postgresql@14/14.8_2/bin/

```


$ ls

clusterdb         oid2name          pg_ctl            pg_restore        pgbench
createdb          pg_amcheck        pg_dump           pg_rewind         postgres
createuser        pg_archivecleanup pg_dumpall        pg_test_fsync     postmaster
dropdb            pg_basebackup     pg_isready        pg_test_timing    psql
dropuser          pg_checksums      pg_receivewal     pg_upgrade        reindexdb
ecpg              pg_config         pg_recvlogical    pg_verifybackup   vacuumdb
initdb            pg_controldata    pg_resetwal       pg_waldump        vacuumlo
```


- postgresql@15 경로

```
 Caveats
This formula has created a default database cluster with:
  initdb --locale=C -E UTF-8 /opt/homebrew/var/postgresql@15
For more details, read:
  https://www.postgresql.org/docs/15/app-initdb.html

postgresql@15 is keg-only, which means it was not symlinked into /opt/homebrew,
because this is an alternate version of another formula.

If you need to have postgresql@15 first in your PATH, run:
  echo 'export PATH="/opt/homebrew/opt/postgresql@15/bin:$PATH"' >> ~/.zshrc

For compilers to find postgresql@15 you may need to set:
  export LDFLAGS="-L/opt/homebrew/opt/postgresql@15/lib"
  export CPPFLAGS="-I/opt/homebrew/opt/postgresql@15/include"

For pkg-config to find postgresql@15 you may need to set:
  export PKG_CONFIG_PATH="/opt/homebrew/opt/postgresql@15/lib/pkgconfig"

To start postgresql@15 now and restart at login:
  brew services start postgresql@15
Or, if you don't want/need a background service you can just run:
  LC_ALL="C" /opt/homebrew/opt/postgresql@15/bin/postgres -D /opt/homebrew/var/postgresql@15
==> Summary
🍺  /opt/homebrew/Cellar/postgresql@15/15.3_2: 3,697 files, 61.4MB
==> Running `brew cleanup postgresql@15`...
Disable this behaviour by setting HOMEBREW_NO_INSTALL_CLEANUP.
Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
```

- 이걸로 해결

```
brew install postgresql
an error message appears
run createdb (because macs don't create username databases after installing PostgreSQL)
execute psql to connect successfully.
```

https://stackoverflow.com/questions/70908116/psql-error-connection-to-server-on-socket-tmp-s-pgsql-5432-failed-fatal

- pgsql 잘 실행 안되서 ㅠㅠ

```
brew uninstall postgresql
brew install postgresql@15
brew services start postgresql@15
brew link postgresql@15 --force
```

https://stackoverflow.com/questions/69754628/psql-error-connection-to-server-on-socket-tmp-s-pgsql-5432-failed-no-such

<hr>

# Learn PostgreSQL Tutorial - Full Course for Beginners
https://youtu.be/qw--VYLpxG4

# Postgresql 설명서
- 15 version https://www.postgresql.org/docs/15/app-initdb.html
https://www.postgresql.kr/docs/9.4/runtime.html

# postgresql - log 확인방법

```
vi /opt/homebrew/var/log/postgresql@14.log
```


https://apple.stackexchange.com/questions/451097/brew-postgresql14-error-on-mac-m2

# Previous versions of postgresql shared the same data directory(Migrate하는 방법

```
=> Installing postgresql@14
==> Pouring postgresql@14--14.7.arm64_ventura.bottle.tar.gz
==> Caveats
Previous versions of postgresql shared the same data directory.

You can migrate to a versioned data directory by running:
  mv -v "/opt/homebrew/var/postgres" "/opt/homebrew/var/postgresql@14"

(Make sure PostgreSQL is stopped before executing this command)

This formula has created a default database cluster with:
  initdb --locale=C -E UTF-8 /opt/homebrew/var/postgres
For more details, read:
  https://www.postgresql.org/docs/14/app-initdb.html

To restart postgresql@14 after an upgrade:
  brew services restart postgresql@14
Or, if you don't want/need a background service you can just run:
  /opt/homebrew/opt/postgresql@14/bin/postgres -D /opt/homebrew/var/postgres
==> Summary
🍺  /opt/homebrew/Cellar/postgresql@14/14.7: 3,314 files, 45.2MB
==> Running `brew cleanup postgresql@14`...
Disable this behaviour by setting HOMEBREW_NO_INSTALL_CLEANUP.
Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
Removing: /Users/globalyoung/Library/Caches/Homebrew/postgresql@14--14.7... (11.7MB)
==> Caveats
==> postgresql@14
Previous versions of postgresql shared the same data directory.

You can migrate to a versioned data directory by running:
  mv -v "/opt/homebrew/var/postgres" "/opt/homebrew/var/postgresql@14"

(Make sure PostgreSQL is stopped before executing this command)

This formula has created a default database cluster with:
  initdb --locale=C -E UTF-8 /opt/homebrew/var/postgres
For more details, read:
  https://www.postgresql.org/docs/14/app-initdb.html

To restart postgresql@14 after an upgrade:
  brew services restart postgresql@14
Or, if you don't want/need a background service you can just run:
  /opt/homebrew/opt/postgresql@14/bin/postgres -D /opt/homebrew/var/postgres
```

# Tutorial

https://news.hada.io/topic?id=9864&utm_source=weekly&utm_medium=email&utm_campaign=202330

PostgreSQL 14의 내부구조(스냅샷, 버퍼캐시, WAL, 잠금, 질의 실행, 각종 색인)에 대해 소개한 무료 이북의 최종본이 지난 3월 즈음에 나왔길래 뒤늦게나마 소개해 봅니다.

PDF 다운로드 : https://edu.postgrespro.com/postgresql_internals-14_en.pdf
1년 전 파트1 공개 소식 : https://news.hada.io/topic?id=6982
