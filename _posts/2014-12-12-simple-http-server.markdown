---
layout: post
title: "Módulo Simple HTTP Server"
date: 2014-12-12 14:04:12 -0200
comments: true
categories: [python]
author: Renan E. 
---


Nesse primeiro post, vou mostrar de maneira rápida como gerar um simples Web server utilizando o módulo <code>SimpleHTTPServer</code> que vem embutido na linguagem python.

<!--more-->

Com esse simples Web server é possivel compartilhar qualquer diretório do sistema em uma rede local "LAN' com uma unica linha de comando, sem a necessidade de instalar e configurar nada.

*As distribuições GNU/Linux mais populares já vêm com Python instalado por padrão.*

#### Iniciando o Web server no diretório share.

```bash
cd share
python -m SimpleHTTPServer 
Serving HTTP on 0.0.0.0 port 8000 ...
192.168.0.14 - - [14/Dec/2014 22:05:11] "GET / HTTP/1.1" 200 -

``` 
No browser de internet de sua preferência digite:
 
<code>http://seu-ip-address:8000</code> 

#### Exemplo:


![](http://i63.fastpic.ru/big/2014/1215/62/a7d65d535559d3f4787c1c1787234c62.png)


Acessar via interface loopback:

<code>http://localhost:8000</code> ou <code>http://127.0.0.1:8000</code>


Caso queira mudar a porta padrão, adicione o numero da porta no final do comando:
```bash
python -m SimpleHTTPServer 8080
Serving HTTP on 0.0.0.0 port 8080 ...
```

___

#### Suporte para Upload de Arquivos:

Este simples Web server não tem suporte para upload de arquivos, porém na internet encontrei um script em python que tem a função de upload.

Baixe o script e salve no diretório a ser compartilhado, no meu caso share/, depois execute o script:

[SimpleHTTPServerWithUpload](http://bones7456.googlecode.com/svn/trunk/SimpleHTTPServerWithUpload.py "Download")


```bash
cd share
wget http://bones7456.googlecode.com/svn/trunk/SimpleHTTPServerWithUpload.py
python SimpleHTTPServerWithUpload.py 
Serving HTTP on 0.0.0.0 port 8000 ...
192.168.0.14 - - [14/Dec/2014 22:15:09] "GET / HTTP/1.1" 200 -

```
Acesse novamente o navegador de internet com <code>http://seu-ip-address:8000</code>:

#### Exemplo:

![](http://i63.fastpic.ru/big/2014/1215/f4/19797345ef3cd5d714c7100ba9a4a2f4.png)



**Referências:**<br>
http://ubuntuguide.net/http-server-support-uploading-files-from-windows-in-ubuntu





