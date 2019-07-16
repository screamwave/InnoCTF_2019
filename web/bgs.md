# BGS

**Web**

I loaded the page and saw that there is nothing interesting that I can visually see even though it is said to be a style challenge from the name.

So I view the source and saw the following.

__Snippet in the .html__
```
<html lang="en"><head>
	<meta charset="UTF-8">
	<title>Котики</title>
	<link rel="stylesheet" href="style.css">
</head>
<body style="background: url(../assets/img/backgrounds/2.jpg) no-repeat; background-size: 100%;">

</body></html>
```

Seeing a css, I followed it and saw:

__Contents of style.css__
```
body {
	background: url(NpwxZFTNbuBfgoiHZIPkagRyUPMaugmr.png) no-repeat;
}
```

When I navigate into the .png, I saw the flag.

```
InnoCTF{HVQMGcpOOmNOMnmQwRNBExEBPFTMgnPQ}
```
