# Sender

## Details 

Author: Vlad Roskov (vos)

We've intercepted this text off the wire of some conspirator, but we have no idea what to do with that.

Get us their secret documents

***intercepted_text.txt***

```
220 ugm.cybrics.net ESMTP Postfix (Ubuntu)
EHLO localhost
250-ugm.cybrics.net
250-PIPELINING
250-SIZE 10240000
250-VRFY
250-ETRN
250-AUTH PLAIN LOGIN
250-ENHANCEDSTATUSCODES
250-8BITMIME
250 DSN
AUTH LOGIN
334 VXNlcm5hbWU6
ZmF3a2Vz
334 UGFzc3dvcmQ6
Q29tYmluNHQxb25YWFk=
235 2.7.0 Authentication successful
MAIL FROM: <fawkes@ugm.cybrics.net>
250 2.1.0 Ok
RCPT TO: <area51@af.mil>
250 2.1.5 Ok
DATA
354 End data with <CR><LF>.<CR><LF>
From: fawkes <fawkes@ugm.cybrics.net>
To: Area51 <area51@af.mil>
Subject: add - archive pw
Content-Type: text/plain; charset="iso-8859-1"
Content-Transfer-Encoding: quoted-printable
MIME-Version: 1.0

=62=74=77=2E=0A=0A=70=61=73=73=77=6F=72=64 =66=6F=72 =74=68=65 =61=72=63=
=68=69=76=65 =77=69=74=68 =66=6C=61=67=3A =63=72=61=63=6B=30=57=65=73=74=
=6F=6E=38=38=76=65=72=74=65=62=72=61=0A=0A=63=68=65=65=72=73=21=0A
.
250 2.0.0 Ok: queued as C4D593E8B6
QUIT
221 2.0.0 Bye

```

When saw the intercepted text, I at first thought it was base64 encoded until I saw the last few characters '0A' which is space in ASCII.
So I assume the data is filled with '=' to mislead us. I just remove '\n', '=' and ' ' in `python` with the following code.

```python
#!usr/bin/env python2
import binascii

mystr= "=6 ... =0A"

mystr = mystr.replace('=', '')
mystr = mystr.replace('\n', '')
mystr = mystr.replace(' ', '')

print(binascii.unhexlify(mystr))
```

Which got me the following:

```text
btw.

passwordforthearchivewithflag:crack0Weston88vertebra

cheers!

```

So I read the .txt file given again and I guessed that I need to login to see more details as there was an email send before this.

So I logged in to the email using `thunderbird` with the credentials below.

```python
#!usr/bin/env python2
'VXNlcm5hbWU6ZmF3a2Vz'.decode('base64')
'UGFzc3dvcmQ6Q29tYmluNHQxb25YWFk='.decode('base64')
```

Logging in with the credentials, I shown an email opening it reveals a zip file.

I used the password `crack0Weston88vertebra` to open the zip file which got me a file in .pdf format.

In the pdf, there was the flag.

```text
cybrics{Y0uV3_G0T_m41L}
```
 
