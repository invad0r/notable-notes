---
tags: [php]
title: php
created: '2019-07-30T06:19:49.206Z'
modified: '2023-03-22T08:31:34.655Z'
---

# php

> general-purpose scripting language

## flags

```sh
php -i 

php -a        # start php repl

php -r        # exec php code in oneline

# inline
php -r '
  echo gethostbyname("foo.bar.domain.net").PHP_EOL; 
  foreach(dns_get_record("foo.bar.domain.net", DNS_A) as $i){ echo $i["ip"].PHP_EOL; };
'
```

## usage

## read from stdin

```php
<?php
$handle = fopen ("php://stdin","r");
$foo = fgets($handle);
print ($foo);
fclose($handle);
```

## log to file

```php
<?php
$fd = fopen($filename, "a");
fwrite($fd, date("Y/m/d h:i:s", mktime())." ".$_SERVER['HTTP_X_FORWARDED_FOR'].PHP_EOL);
if(is_array($msg)) {
  foreach($msg as $key => $val) { fwrite($fd, $key.":".$val . "\n"); }
}
fclose($fd);
```

## simple mailer

```php
<?php
/* composer.json: { "require": { "phpmailer/phpmailer": "^5.2" } } */
require 'vendor/autoload.php';
$mail = new PHPMailer;
$mail->isSMTP();
$mail->Host       = 'smtp.host.com';
$mail->SMTPAuth   = true;
$mail->Username   = 'user@host';
$mail->Password   = '*******';
$mail->SMTPSecure = 'tls';
$mail->Port       = 587;
$mail->CharSet    = "UTF-8";
$mail->setFrom('it@host', 'Mailer');
$mail->addAddress('user@host', 'Foo Bar');
$mail->Subject = 'Subject: ä Ä ö Ö ü Ü';
$mail->Body    = 'hello user, ...';
if(!$mail->send()) {
    echo 'Message could not be sent.';
    echo 'Mailer Error: ' . $mail->ErrorInfo;
} else {
    echo 'Message has been sent';
}
```

## see also

- [[composer]]
- [[python]]
- [[scala]]
- [[irb]]
