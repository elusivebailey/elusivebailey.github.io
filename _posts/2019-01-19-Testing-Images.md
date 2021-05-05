---
layout: post
title: "Embedded Images and PDFs in Markdown"
author: "Bailey Wagner"
---

Ever wondered how to embed your PDFs or images in Markdown from your perfectly cloud-stored files? Look no futher, future-me! Here's a short guide for embedding your images and PDFs from Google Drive and Dropbox in your super cool webpage.


- - -
## Embedding Images
- - -

A simple how-to:
1. Make sure your image is public and shareable
2. Get the generic code (below) from Google Drive or Dropbox
3. Get the shareable link for the image
4. Paste it in the correct place and make any adjustments
5. Enjoy your beautifully embedded image



### Images stored in Dropbox

There's a tiny trick to get the Dropbox shareable link you have for your picture to work:

```
https://www.dropbox.com/s/va2bwyd2l6u95pu/Ari_in_a_sink.JPG?dl=0
```

needs to change to

```
https://www.dropbox.com/s/va2bwyd2l6u95pu/Ari_in_a_sink.JPG?raw=1
```

by switching the "dl=0" to "raw=1" at the end of the code. This allows the image to be embedded.


#### General Code Layout

```
![Alternative text](https://www.dropbox.com/s/YOUR_IMAGE_ID/YOUR_IMAGE_NAME?raw=1 "A neat little title")
```


#### Example Code Layout

```
![DropBox image couldn't load](https://www.dropbox.com/s/va2bwyd2l6u95pu/Ari_in_a_sink.JPG?raw=1 "Ari in a sink")
```

The code above will produce the following image:

![Dropbox image couldn't load](https://www.dropbox.com/s/va2bwyd2l6u95pu/Ari_in_a_sink.JPG?raw=1 "Ari in a sink")

<br>

### Images stored in Google Drive

For Google Drive, each image has an ID. You'll use this *instead* of the shareable image link from Google.

The shareable link from Google:

```
https://drive.google.com/open?id=1hPJmMv4fye6x_4_upF9LKI44yE0F8vXb
```

The ID number from that link:

```
1hPJmMv4fye6x_4_upF9LKI44yE0F8vXb
```


#### General Code Layout

```
![Alternative text](https:drive.google.com/uc?id=YOUR_IMAGE_ID)
```

#### Example Code Layout

```
![Google Drive image couldn't load](https://drive.google.com/uc?id=1hPJmMv4fye6x_4_upF9LKI44yE0F8vXb "A title if you want one")
```

The code above will produce the following image:

![Google Drive image couldn't load](https://drive.google.com/uc?id=1hPJmMv4fye6x_4_upF9LKI44yE0F8vXb "Thea in a sink")

<br>

- - -

## Embedding PDFs
- - -

So, Markdown doesn't really work for embedding PDFs, but we can use HTML (to the rescue) to make up for that.



### PDFs stored in Dropbox

The same rule of changing the ending of the shareable link from "dl=0" to "raw=1" for embedding images also applies to embedding PDFs.


#### General Code Layout

This code is stolen straight from [Stack Overflow](https://stackoverflow.com/questions/291813/recommended-way-to-embed-pdf-in-html).

```html
<object data="http://yoursite.com/the.pdf" type="application/pdf" width="750px" height="750px">
    <embed src="http://yoursite.com/the.pdf" type="application/pdf">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="http://yoursite.com/the.pdf">Download PDF</a>.</p>
    </embed>
</object>
```


#### Example Code Layout

My Dropbox link (edited for "raw=1" at the end):

```
https://www.dropbox.com/s/y39hietj1ht9sf1/PHY%20350%20Note%20Sep%2019%2C%202016.pdf?raw=1
```

All I did was copy this link and paste it wherever I saw http://yoursite.com/the.pdf in the General Code Layout above.

```html
<object data="https://www.dropbox.com/s/y39hietj1ht9sf1/PHY%20350%20Note%20Sep%2019%2C%202016.pdf?raw=1" type="application/pdf" width="750px" height="750px">
    <embed src="https://www.dropbox.com/s/y39hietj1ht9sf1/PHY%20350%20Note%20Sep%2019%2C%202016.pdf?raw=1">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="https://www.dropbox.com/s/y39hietj1ht9sf1/PHY%20350%20Note%20Sep%2019%2C%202016.pdf?raw=1">Download PDF</a>.</p>
    </embed>
</object>
```

<object data="https://www.dropbox.com/s/y39hietj1ht9sf1/PHY%20350%20Note%20Sep%2019%2C%202016.pdf?raw=1" type="application/pdf" width="750px" height="750px">
    <embed src="https://www.dropbox.com/s/y39hietj1ht9sf1/PHY%20350%20Note%20Sep%2019%2C%202016.pdf?raw=1">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="https://www.dropbox.com/s/y39hietj1ht9sf1/PHY%20350%20Note%20Sep%2019%2C%202016.pdf?raw=1">Download PDF</a>.</p>
    </embed>
</object>


<br>

### PDFs stored in Google Drive

For Google Drive embedded PDF's, this example uses iframe ([it can also be done other ways](https://gist.github.com/tzmartin/1cf85dc3d975f94cfddc04bc0dd399be)).

#### General Code Layout

Again, [Stack Overflow](https://stackoverflow.com/questions/44164367/how-to-embed-google-drive-document-pdf-in-blogger-post) was my best friend for figuring out what the general code needs to look like:

```html
<iframe src="https://docs.google.com/viewer?srcid=[YOUR_PDF_ID]&pid=explorer&efh=false&a=v&chrome=false&embedded=true" width="750px" height="750px"></iframe>
```

#### Example Code Layout

My Google Drive shareable link:

```
https://drive.google.com/open?id=112qQkHbCybu0wR4FdbOvSnDHVP0CevAo
```

and the following ID:

```
112qQkHbCybu0wR4FdbOvSnDHVP0CevAo
```

All you should have to do is edit the link to add your PDF ID.

```html
<iframe src="https://docs.google.com/viewer?srcid=112qQkHbCybu0wR4FdbOvSnDHVP0CevAo&pid=explorer&efh=false&a=v&chrome=false&embedded=true" width="750px" height="750px"></iframe>
```

<iframe src="https://docs.google.com/viewer?srcid=112qQkHbCybu0wR4FdbOvSnDHVP0CevAo&pid=explorer&efh=false&a=v&chrome=false&embedded=true" width="750px" height="750px"></iframe>

<br>

Thanks for reading and happy coding!
