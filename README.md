#(For PayU Ukraine and Russian ONLY)
------

#Модуль для CMS Melbis
======

#Установка
-------------
1). Разместите папку payu в каталог /pay_mod/ <br>
2). Откройте клиентское приложение Melbis Shop. Зайдите в раздел Настройки - Способы оплаты и создайте новый вариант оплаты  <br>
![Скриншот][1]
3). В поле HTML-код для совершения оплаты вставьте текст: <br>

```HTML
<P align=center><STRONG><FONT color=#ff0000>Внимание!</FONT></STRONG> </P>
<P align=center><STRONG>Транзакция платежа осуществляется непосредственно на защищенном сайте компании PayU.</STRONG></P><BR>
<P align=center><INPUT onclick="document.location='./pay_go.php?type=payu&amp;{PHPSESSID}'" type=button value="Оплатить"></P>
```

4). Выполните отправку данных на сервере из клиентской программы Melbis Shop. <br>

5). Зайдите по FTP на ваш сервер в директорию, где установлен магазин и откройте для редактирования файл: /pay_mod/payu/vars.php 

>	define('__MERCHANT__', 'MERCHANT'); # идентификатор мерчанта
>	define('__SECRETKEY__', 'SECURE KEY'); # секретный ключ
>
>define('__LUURL__', ''); # ссылка для LiveUpdate. Для Украинских мерчантов оставлять пустым. <br>
>						 # Для мерчантов из России : https://secure.payu.ru/order/lu.php
>
>define('__DEBUG__', '1'); # Режим тестирования.  После тестирования - обязательно выключить (поставить 0)
>
>define('__BUTTON__', true); # true - Использовать автопереадресацию. можно вписать свой код кнопки.  
>
>define('__CURRENCY__', "RUB"); # Валюта мерчанта
>
>define('__LANGUAGE__', "RU"); # Язык страницы оплаты


Ссылка IPN : 

http://{сайт}/pay_get.php?type=payu


[1]: https://raw.github.com/PayUUA/Melbis/master/screenshot.jpg
