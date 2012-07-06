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
Get the first page of a PDF:  
`pdftk pdfs/52-6078041_990PF_200706.pdf shuffle 1 output 52-607.pdf`

Turn that first page into an image:  
`./pdf-splitter 52-607.pdf 'img/%.d.jpg' 1200px`

Get a section of the page to process:  
`convert img/1.jpg -crop 490x20+185+225 img/1.crop.jpg`

OCR the image (you'll get a file named 1.txt):  
`tesseract img/1.crop.jpg 1`
