# postgresql_gy

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
