# postgresql_gy

# Learn PostgreSQL Tutorial - Full Course for Beginners
https://youtu.be/qw--VYLpxG4

# Postgresql 설명서
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
