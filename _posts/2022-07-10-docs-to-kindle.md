# Converting Documents for Kindle (or Other E-Readers)
I received a Kindle this past Christmas and have been devouring books with it since. I have always loved physical books, but reading on the Kindle has a convenience that physical books don’t quite offer. It’s easy to flip the cover and continue reading, and no book is too bulky to carry around. In fact, the number of books that it can store and let me easily carry along for travel has been a huge benefit.

There are myriad books available from Amazon, but I have found myself checking more books out from the library than purchasing them. Even more reading material exists online from articles, blog posts, research papers, textbooks, etc., and I find myself wanting to read them on the Kindle. So, I have dipped a toe into the world of document conversion and formatting, trying to find the best way to reformat online text. Despite the ease of getting a document onto the Kindle, formatting for the limited features and smaller screen takes a bit of work.

## Several different options
### K2pdfopt
There are a ton of PDFs online. Most research papers and online textbooks come in this format, and any web page can be “printed” to PDF. [k2pdfopt](https://www.willus.com/k2pdfopt/) re-formats a PDF for displaying on an e-reader. It can handle a lot of different formatting options, but does require some experimentation to get the results you want. Overall, this is the best tool I have found for dealing with PDFs.

### Calibre ebook-convert
[Calibre](https://calibre-ebook.com/) is an e-book management software package that includes an e-book conversion tool called [ebook-convert](https://manual.calibre-ebook.com/generated/en/ebook-convert.html). It handles a lot more than just PDF, inlcuding HTML, EPUB, MOBI, docx, and more. The e-book intended extension, like EPUB and MOBI, do not require as much prior formatting as the Kindle handles some of that itself. This has been my go to for converting HTML files to e-reader formats.

### Jupyter-nbconvert
The [Jupyter notebook ecosystem](https://jupyter.org/) allows you to convert Jupyter notebooks from the ipynb format into PDFs, latex, HTML, markdown, and a few others via [nbconvert](https://nbconvert.readthedocs.io/en/latest/). This is more of a niche format for programming tutorials and texts, it’s useful if you find a series of notebooks (or even just one long notebook) that you would prefer to read on the Kindle. There are some additional steps to render math text properly, which can be done with the next tool.

### Pandoc
While nbconvert is only intended to convert notebooks to other formats, [Pandoc](https://pandoc.org/index.html) can convert most document formats to any other formats. But I have found it very useful for converting latex to HTML with rendered math tex equations. Pandoc can even take saved HTML webpages, which can save images as separate files, and convert them to a standalone format that is easier to send to the Kindle.

## Reading how you want to
My results have been mixed depending on the source and formatting of the original document. I’m still figuring out the work flow, and each document takes some tinkering to find the best tools and settings. There are some “pre-built” browser extensions that easily convert a web page for the Kindle. There is Amazon’s [send to Kindle](https://chrome.google.com/webstore/detail/send-to-kindle-for-google/cgdjpilhipecahhcilnafpblkieebhea?hl=en), which is a chrome only extension. A more flexible option is [Push to Kindle](https://www.fivefilters.org/push-to-kindle/), which is available on other platforms and allows you to download the file directly, meaning this should work well for other e-readers too.

I wanted something a little more hands on, however, and have felt surprised at the amount of effort it does take to format something well (or at all) for an e-reader. With all the content available online, most is already formatted as web pages (i.e., broken across multiple files) or PDFs (i.e., the printed page), tying content nearly inextricably to the medium with which it is consumed. That we can’t just pull the text out for another format may not be too surprising in retrospect (or for some readers), but it is something I haven’t fully dealt with before. 

