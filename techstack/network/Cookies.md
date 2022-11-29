#network #http 

- Cookie is sent in every [request](/request) but within [HTTPS](/techstack/network/HTTPS.md) encrypted.
- is stored locally in the browser
	- browser is acting like a [sandbox](/sandbox)
- valid until expired

Create cookie:
```js
document.cookie="username=John Doe; expires=Thu, 27 Jul 2021, 12:00:00 GMT";
```
```php
<? php
	$meanvalue = "hello world";
	setcookie("test", $mean);
	setcookie("Test", $mean value, time()+3600); # 1 hour valid.
?>
```
