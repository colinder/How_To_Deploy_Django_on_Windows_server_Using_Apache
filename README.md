# How_To_Deploy_Django_on_Windows_server_Using_Apache



#### 개발 환경 세팅
Download Links
Apache - https://www.apachelounge.com/download/<br>
Dev C++ - https://visualstudio.microsoft.com/visual-cpp-build-tools/
<br>
<br>
<br>

#### `C:/Apache24/bin/` 위치에서 CMD를 열고 아래 명령어 실행
```
$ httpd.exe -k install
$ httpd.exe -k start
```
<br>
<br>
<br>

#### mod-wsgi 설정값 확인 명령어
```
mod_wsgi-express module-config
```
<br>
<br>
<br>                      
    
#### Apache Django Project conf setting
> C:\Apache24\conf 로 이동해 httpd.conf 파일 맨 아래 추가 
```
LoadFile "c:/python37/python37.dll"
LoadModule wsgi_module "c:/python37/lib/site-packages/mod_wsgi/server/mod_wsgi.cp37-win_amd64.pyd"
WSGIPythonHome "c:/python37"
WSGIScriptAlias / "C:/Users/navar/Desktop/webproject/webproject/wsgi.py"
WSGIPythonPath "C:/Users/navar/Desktop/webproject/"

<Directory "C:/Users/navar/Desktop/webproject/webproject/">
    <Files wsgi.py>
        Require all granted
    </Files>
</Directory>

Alias /static "C:/Users/navar/Desktop/webproject/static/"
<Directory "C:/Users/navar/Desktop/webproject/static/">
    Require all granted
</Directory>
```
