# warmup

## Details

Warmup (Web, Baby, 10 pts)
Author: George Zaytsev (groke)

E_TOO_EASY

Just get the flag

## Solution
I tried to go to the site given `http://45.32.148.106`, I got redirected to `http://45.32.148.106/final.html`

I did not realized it at first, but it seems like there is a Javascript from index.html that redirected me to final.html

When I used `curl` to get the page, there was a section that says that the string is base64 encoded.

When I decoded `Y3licmljc3s0YjY0NmM3OTg1ZmVjNjE4OWRhZGY4ODIyOTU1YjAzNH0=` I got the flag.


```
cybrics{4b646c7985fec6189dadf8822955b034}
```

