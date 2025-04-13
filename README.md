# LLMs Project/Lab

## docsum.py 
**`docsum.py`** contains Python code that uses the Groq LLaMA models to summarize a variety of documents and images. It supports both local files and web URLs.

## What it Supports

| Input Type            | Examples                                  |
|-----------------------|-------------------------------------------|
| Plain Text            |  essay.txt, README, declaration           | 
| HTML Files            |  page.html                                | 
| PDF Files             |  research_paper.pdf                       | 
| Images (local)        |  photo.jpg                                |
| Images (URL)          |  https://example.com/image.jpg            |
| Web Pages             |  https://nytimes.com/article              |

## How to Use it

Make sure to install anything necessary from the list of imports used in the `docsum.py` file (note: textract was not working for my .pdf files, so i researced *PyMuPDF*, which is labeled as *fitz*, to use instead). It's also required to get your own personal **Groq API key** and set it up in a file named `.env`. You can input the following code into the *.env* file:
`GROQ_API_KEY=your_API_key`
Now, run from the command line like this and it will generate a summary of whatever it's analyzing:
`python3 docsum.py filename`
or,
`python3 docsum.py url`

### Here are some examples of the output when I ran the following commands

filename = docs/news-mx.html
<pre> ```bash $ python3 docsum.py docs/news-mx.html  The text appears to be a collection of coding snippets, including JavaScript, CSS, and HTML, that make up the El País website. The code includes settings and configurations for content, advertising, and user subscription links, as well as styles and animations for visual elements. Meanwhile, the text also includes news articles about the US Supreme Court's decision to allow the deportation of immigrants accused of being involved with a criminal organization in Venezuela. ``` </pre>