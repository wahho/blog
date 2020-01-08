20200108-phpbrew-install-memo.md
-----

* homebrewによる各種ライブラリアップデートによってphpが使えなくなったので、復旧時のコマンドメモ

```
phpbrew list -v

phpbrew install 7.3.6 +default +mysql +openssl=$(brew --prefix openssl) +bz2="$(brew --prefix bzip2)" +zlib="$(brew --prefix zlib)"
phpbrew install 7.2.12 +default +mysql +openssl=$(brew --prefix openssl) +bz2="$(brew --prefix bzip2)" +zlib="$(brew --prefix zlib)"
phpbrew install 7.0.15 +default +mysql +openssl=$(brew --prefix openssl) +bz2="$(brew --prefix bzip2)" +zlib="$(brew --prefix zlib)" +curl="$(brew --prefix curl)"
phpbrew install 5.6.35 +default +mysql +openssl=$(brew --prefix openssl) +bz2="$(brew --prefix bzip2)" +zlib="$(brew --prefix zlib)" +curl="$(brew --prefix curl)"

```
