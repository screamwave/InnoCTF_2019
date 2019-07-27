# COOL STYLE

**Web**

I loaded the page and saw that there is nothing interesting that I can visually see even though it is said to be a style challenge from the name.

So I view the source and saw the following.

__Snippet in the .html__
```
<link rel="stylesheet" href="../assets/css/ITXFDqiVeKRuJrsUr.css">
<link rel="stylesheet" href="../assets/css/nkMgODvQxXiPKDOqtyX.css">
<link rel="stylesheet" href="../assets/css/niQImeIdaSLBzQyuzgsE.css">
<link rel="stylesheet" href="../assets/css/oWdjjPzSwyiyqztoaWub.css">
<link rel="stylesheet" href="../assets/css/CDyKMbalaWcuZalMMxuuq.css">
<link rel="stylesheet" href="../assets/css/TPUgqYfrMDzgtvDDXzr.css">
<link rel="stylesheet" href="../assets/css/FPBbBjfopzmeIKURUlM.css">
<link rel="stylesheet" href="../assets/css/{JLeyolNGmCJmbyZBOXK.css">
<link rel="stylesheet" href="../assets/css/gosZUJyudiMPOqTGpaiu.css">
<link rel="stylesheet" href="../assets/css/pJGZytvkRXFWhldqhluNF.css">
<link rel="stylesheet" href="../assets/css/FeHqteKDroCUHFPc.css">
<link rel="stylesheet" href="../assets/css/EIhyyXDiFYiEETqpd.css">
<link rel="stylesheet" href="../assets/css/uJKawPkTJPowONosgT.css">
<link rel="stylesheet" href="../assets/css/QCTDzMZTEdjMqZtPD.css">
<link rel="stylesheet" href="../assets/css/KMRVfFMkrJfbjLdzsqAlk.css">
<link rel="stylesheet" href="../assets/css/IORtCquoWrhbzXbaUri.css">
<link rel="stylesheet" href="../assets/css/QbDvMjjWvlGzYxNmy.css">
<link rel="stylesheet" href="../assets/css/EWnxSXaqEYGNPULn.css">
<link rel="stylesheet" href="../assets/css/NxXILRXfLvRmQmmO.css">
<link rel="stylesheet" href="../assets/css/MtNvSbJtnClKhQytgAO.css">
<link rel="stylesheet" href="../assets/css/tnJyDOpcJLwWQkAzy.css">
<link rel="stylesheet" href="../assets/css/DAoaGjfopwmTHYsjqXh.css">
<link rel="stylesheet" href="../assets/css/fGbmmlSvdqEgbfKaBvm.css">
<link rel="stylesheet" href="../assets/css/REXvSCgRFtAHCnsgJx.css">
<link rel="stylesheet" href="../assets/css/tsRBWuzQohjfLyVqvpbTr.css">
<link rel="stylesheet" href="../assets/css/mKkygErDYxSnaYcipWvd.css">
<link rel="stylesheet" href="../assets/css/EbOousEXxrtLWTsbG.css">
<link rel="stylesheet" href="../assets/css/FQheGaNdTKihZmAUOjoNv.css">
<link rel="stylesheet" href="../assets/css/KjebJhcszhSKIDATzzK.css">
<link rel="stylesheet" href="../assets/css/devCzZivcUCypTqvHvpm.css">
<link rel="stylesheet" href="../assets/css/CHWsMNhLnVwhMgGWhgU.css">
<link rel="stylesheet" href="../assets/css/FmtMnojFgaZLZWeeGVfDR.css">
<link rel="stylesheet" href="../assets/css/tKqkzKSStRKoTUjejrwNg.css">
<link rel="stylesheet" href="../assets/css/WqTTNkobDTYLEyDARPOGr.css">
<link rel="stylesheet" href="../assets/css/anYpYCgDgSOozOZtdXW.css">
<link rel="stylesheet" href="../assets/css/VuXrcRbmKVluqoGiyyZYq.css">
<link rel="stylesheet" href="../assets/css/ALiUzDJMEdClYLxcbUbVk.css">
<link rel="stylesheet" href="../assets/css/uMMZFxYwpElnGCXPkBVI.css">
<link rel="stylesheet" href="../assets/css/OGQpYxJgjrgANGNvC.css">
<link rel="stylesheet" href="../assets/css/TnEOQhiwVeVDqxsx.css">
<link rel="stylesheet" href="../assets/css/}QcOAcqUkRYmsNHsmtL.css">

```

Seeing a list of css being loaded, I tried to open the page but to no avail.

Later I tried to base64 decode each of the .css line but it wasn't encoded in base64 so it gave gibberish text.

I then looked at the source carefully and realized that for the first few lines, every .css file's first character corresponds to the flag format.

I strip the text to get the first character of every line's resources and I got the flag.

```
InnoCTF{gpFEuQKIQENMtDfRtmEFKdCFtWaVAuOT}
```
