# ROBOTS

When I visited the site, there was nothing there but the string

__Content in the .html__
```
Hello WORLD!
```

Seeing that the name of the challenge is robots, I tried to navigate to /robots.txt

Surprise surprise, there was a robots.txt with the following.

__Contents of style.css__

```
Disallow: /*/super-secret-admin-panel

```

So I tried to nagivate to `/rAbCilIPOIvDCrjeHIIRDPuPMzARtYUp/super-secret-admin-panel` and I was greeted with a login page.

I then tried to SQL inject it with `' or 1=1 #' in either of the fields and I was able to login and the see flag.

```
InnoCTF{tsZYpJAYdHjXBJKIoZrwCpWZiAaREaHP}
```

