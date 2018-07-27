# MobileSystemGB

### URLs

| Name | Description |
| ------ | ------- |
| gameboy.datacenter.ne.jp | Website that Mobile Trainer uses to enstabilish a connection |
| mail.xxxxx.dion.ne.jp | SMTP Mail Server |
| pop.xxxxx.dion.ne.jp | POP3 Mail Server |

### WebServer

Add the following line to your httpd.conf, this forces Apache to send HTTP 1.0 response rather than 1.1

`BrowserMatch "CGB-B9AJ-00" force-response-1.0 downgrade-1.0`

The datacenter index file is located at: 01/CGB-B9AJ/index.html

NOTE: My script replace index.html with index.php.

### Web Mail

You need a working POP3 and SMTP Server.

The following configuration is done with hWebMail.

First choose the subdomain of your web server, i used 'gbaa'.

Add to domains the domain name:
`<your subdomain>.dion.ne.jp`

In this case it will be:
`gbaa.dion.ne.jp`

Mobile Trainer uses Email username and password as authentication, you need to add a new email account.

An example username could be this:
`test@gbaa.dion.ne.jp`

NOTE: The password must have one number and one letter, otherwise Mobile Trainer will not accept it.

