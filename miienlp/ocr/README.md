# Optical Character Recognition (OCR)

## What does it do?
This platform will perform OCR on images, converting images containing text into text files. Specifically, it will perform [Google Vision OCR](https://cloud.google.com/vision/docs/ocr). 

## OCR Software Comparison Review

Over the past ~5 years, researchers have consistently identified Google Cloud Vision OCR as the best technology for converting images to text. In one study, [Tafti et al.](https://www.researchgate.net/publication/310645810_OCR_as_a_Service_An_Experimental_Evaluation_of_Google_Docs_OCR_Tesseract_ABBYY_FineReader_and_Transym) compared the accuracy of Google Docs (now Google Vision), Tesseract, ABBYY FineReader, and Transym OCR methods for over one thousand images and 15 image categories, and found that Google Vision generally outperformed other methods. In particular, Google Vision’s accuracy with digital images was 4% better than any other method. Additionally, the standard deviation of accuracy for Google Vision was quite low, suggesting that the quality of OCR does not drastically change from one image to the next. [Han and Hickman](https://source.opennews.org/articles/so-many-ocr-options/) compared seven OCR tools and also found Google Vision to be superior, specifically when extracting results from low resolution images. In another study that focused on comparing results from multiple image formats (jpg, png, tiff, etc),  [Vijayarani and Sakila](https://www.researchgate.net/publication/281583162_Performance_Comparison_of_OCR_Tools) found that Google Docs surpassed all other OCR tools. While Google Vision is dominant, it is not free. A cost-free alternative technology, is Tesseract. While Tesseract's performance does not match that of Google Vision's, it is close.

**IMPORTANT** 

For more details, see:
- [example](https://github.com/miielab/miienlp/blob/main/examples/ocr_example.md) 
- [setup instructions for UChicago MiiE Lab RA ONLY](https://github.com/miielab/miienlp/blob/main/documentation/miie_ra_documentation/ocr.md)
- [setup instructions for running OCR locally](https://github.com/miielab/miienlp/blob/main/documentation/user_documentation/ocr.md)

### How to run OCR using Tesseract

1. Install Tesseract using the [guide](https://tesseract-ocr.github.io/tessdoc/Compiling.html) by Tesseract for installing elsewhere/without root.
```
./autogen.sh
./configure --prefix=$HOME/local/
make
make install
```
  
2. Check if Tesseract is installed correctly.
```
tesseract --version
```
The output should look like the following:
```
tesseract 5.3.1-23-gbb88
 leptonica-1.82.0
  libgif 5.2.1 : libjpeg 8d (libjpeg-turbo 2.1.5.1) : libpng 1.6.40 : libtiff 4.5.1 : zlib 1.2.11 : libwebp 1.3.0 : libopenjp2 2.5.0
 Found AVX512BW
 Found AVX512F
 Found AVX512VNNI
 Found AVX2
 Found AVX
 Found FMA
 Found SSE4.1
 Found libcurl/7.85.0 SecureTransport (LibreSSL/3.3.6) zlib/1.2.11 nghttp2/1.47.0
```

3. Run Tesseract on a test image. You can access some examples and tutorials [here](https://tesseract-ocr.github.io/tessdoc/Command-Line-Usage.html#simplest-invocation-to-ocr-an-image).
```
tesseract imagename outputbase
```
Example:
```
tesseract ../../../examples/test_data/test_scans/maryjosgrandmoth00udry_19.jpg - -l eng
```
Output:
```
Estimating resolution as 570
Detected 88 diacritics
L

-4. b
20N
R
. “

| \ § 4 =
".- R “w
- . ~ “Z s 5\ i
< F )
/ t. - 5 \
I AN N |
4 i a e o=
; o d ."F.-' 4 o
y * o o
] L e -
i Yo% L1 1A
T W N
- $ "N
a Ve
3 b o &y
4 IR v
\-.M l =Y ‘. ’,.:FJ' ’
,}' ol VL

They made blackberry jam and carried
the jars into Grandmother’s little pantry to
store for winter.

Sometimes they all drove over to the river
and went fishing. On hot summer evenings,
they had supper on the porch—fried fish,
roasting ears, tomatoes, and green apple pie.

In the fall, they gathered hickory nuts
and black walnuts in the woods. And from
Grandmother’s garden Mary Jo and Jeff each
picked out a pumpkin to take back into town
for Halloween.
```







