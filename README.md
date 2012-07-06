Thoughts / approaches to processing 990s 
========================================

Included in this toybox:
------------------------
* Several sample PDFs!
* A set of commands to convert PDFs to plain text!
* A compiled version of [pdf-splitter](https://github.com/thejefflarson/pdf-splitter) for mac!

You'll need:
------------
* [pdftk](http://www.pdflabs.com/docs/install-pdftk/)
* Some stuff from brew (make sure to run `brew update` first):
    * `brew install imagemagick`
    * `brew install tesseract`

OCR Ahoy!
---------
To get the first page of a PDF:  
`pdftk pdfs/56-6060716_990PF_200609.pdf shuffle 1 output 52-606.pdf`

To turn a PDF into an image:  
`./pdf-splitter 52-606.pdf 'img/%.d.jpg' 1200px`

To get sections of a page:  
`convert img/1.jpg -crop 490x20+185+225 img/1.crop.jpg`

To process the image (you'll get a file named 1.txt):  
`tesseract img/1.crop.jpg 1`
