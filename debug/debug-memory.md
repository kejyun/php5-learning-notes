# 記憶體

當在使用 Composer 安裝套件時，出現記憶體不足的狀況，此時可以調高 PHP 使用的記憶體

> Composer require runs out of memory. PHP Fatal error: Allowed memory size of 1610612736 bytes exhausted

因為 Composer 使用的是 php cli 安裝，所以記憶體設定檔案會是在 `cli` 目錄下

> sudo vim /etc/php/7.4/cli/php.ini

## 取得目前記憶體設定

```shell
php -r "echo ini_get('memory_limit').PHP_EOL;"
```

## 將記憶體使用設定無上限

```shell
; Use -1 for unlimited or define an explicit value like 2G
memory_limit = -1
```

## 強制指定此執行的記憶體限制

```shell
php -d memory_limit=-1 composer.phar require hwi/oauth-bundle php-http/guzzle6-adapter php-http/httplug-bundle
```

## 觀看 php 設定

```shell
php --ini
```

## 參考資料
* [symfony - Composer require runs out of memory. PHP Fatal error: Allowed memory size of 1610612736 bytes exhausted - Stack Overflow](https://stackoverflow.com/questions/49212475/composer-require-runs-out-of-memory-php-fatal-error-allowed-memory-size-of-161)
