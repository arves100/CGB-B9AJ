# CGB-B9AJ

***NOTE: THIS REPOSITORY IS NO LONGER MAINTAINED, IT WILL NOT BE DELETED FOR ARCHIVAL REASON, PLEASE LOOK AT [REONTeam](https://github.com/REONteam) IF YOU NEED AN UPDATED VERSION OF THE SCRIPT AS WELL AS EMAIL/WEB SERVER CONFIGURATIONS***

### URLs

| Name | Description |
| ------ | ------- |
| gameboy.datacenter.ne.jp | Website that Mobile Trainer uses to enstabilish a connection |
| mail.xxxxx.dion.ne.jp | SMTP Mail Server |
| pop.xxxxx.dion.ne.jp | POP3 Mail Server |

### BGB
Listen to BGB to default port, then launch mobilesystem.py.

First use Mobile Trainer to setup your account, then use any compatible game.

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

### DNS Hacking
dns_server_replacement = {
	"gameboy.datacenter.ne.jp" : b'\x7F\x00\x00\x01',
	"mail.gbaa.dion.ne.jp" : b'\x7F\x00\x00\x01',
	"pop.gbaa.dion.ne.jp" : b'\x7F\x00\x00\x01'
}

This handle DNS rewriting.

It expects the domain to be rewrited (example gameboy.datacenter.ne.jp) with a bytearray telling the 4 digit of the ip.

Example: if your IP is 127.0.0.1, you do an HEX of the four digits (splitted by '.')

so 127 became 0x7f, 0 is 0x00 and 1 is 0x01. So the ip is 0x0f0x000x000x01.

In python 0x became \x.


