# Nextcloud

## Additional configuration

`/var/www/html/config/config.php`

```diff
// ...
-  'overwrite.cli.url' => 'http://nextcloud.secondhomelab.com',
+  'overwrite.cli.url' => 'https://nextcloud.secondhomelab.com',
+  'overwriteprotocol' => 'https',
//...
```
