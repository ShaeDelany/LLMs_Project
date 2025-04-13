# LLMs Project/Lab

## docsum.py 
**`docsum.py`** contains Python code that uses the Groq LLaMA models to summarize a variety of documents and images. It supports both local files and web URLs.

## What it Supports

| Input Type            | Examples                                  |
|-----------------------|-------------------------------------------|
| Plain Text            |  constituion-mx.txt, declaration          | 
| HTML Files            |  news-mx.html                             | 
| PDF Files             |  research_paper.pdf                       | 
| Images (local)        |  photo.jpg                                |
| Images (URL)          |  https://www.cmc.edu/sites/default/files/about/images/20170213-cube.jpg        |
| Web Pages             |  https://elpais.com/us/                   |

## How to Use it

Make sure to install anything necessary from the list of imports used in the `docsum.py` file (note: *textract* was not working for my .pdf files, so i researced *PyMuPDF*, which is labeled as *fitz*, to use instead). It's also required to get your own personal **Groq API key** and set it up in a file named `.env`. You can input the following code into the *.env* file:
`GROQ_API_KEY=your_API_key`
Now, run from the command line like this and it will generate a summary of whatever it's analyzing:
`python3 docsum.py filename`
or,
`python3 docsum.py url`

### Here are some examples of the output when I ran the following commands

filename = docs/news-mx.html
<pre>$ python3 docsum.py docs/news-mx.html  
Summary = The text appears to be a collection of coding snippets, including JavaScript, CSS, and HTML, that make up the El País website. The code includes settings and configurations for content, advertising, and user subscription links, as well as styles and animations for visual elements. Meanwhile, the text also includes news articles about the US Supreme Court's decision to allow the deportation of immigrants accused of being involved with a criminal organization in Venezuela.</pre>
filename = docs/constitution-mx.txt
<pre>$ python3 docsum.py docs/constitution-mx.txt
Summary = The Mexican Constitution recognizes the uniqueness and indivisibility of the Mexican Nation and its pluricultural composition, guaranteeing the rights and autonomy of indigenous peoples. The constitution outlines the principles and rules for governance, including the structure and powers of the federal government, states, and municipalities, as well as the rights and responsibilities of public servants. Additionally, the constitution establishes specific provisions for labor and social welfare, including the rights of workers and the responsibilities of employers.</pre>
filename = docs/research_paper.pdf
<pre>$ python3 docsum.py docs/research_paper.pdf
The authors propose a new pretraining method called DOCSPLIT, specifically designed for large documents, which forces models to consider the global context of a document using a contrastive loss. DOCSPLIT outperforms other pretraining methods on document classification, few-shot learning, and document retrieval tasks, and can be applied to any model architecture. The results suggest that DOCSPLIT can significantly improve the performance of models on large documents, with the best results achieved in few-shot text classification tasks.</pre>
filename = https://elpais.com/us/
<pre>$ python3 docsum.py https://elpais.com/us/
The text appears to be a collection of code, primarily in JavaScript and CSS, for a website or application, defining various functions, classes, and styles for elements, layouts, and typography. The text also includes news articles and updates from various fields, discussing topics such as politics, economy, culture, and technology.</pre>
filename = https://www.cmc.edu/sites/default/files/about/images/20170213-cube.jpg
<pre>$ python3 docsum.py https://www.cmc.edu/sites/default/files/about/images/20170213-cube.jpg
The image depicts a modern glass building with a pool of water in front of it, surrounded by other buildings. The main subject or scene depicted in this image is likely an office or educational facility, given the presence of seating areas and what appears to be meeting spaces.

**Key Features:**

* A large glass building with a black roof
* A pool of water in front of the building, reflecting the lights from inside
* Several other buildings surrounding the main structure
* Seating areas and what appears to be meeting spaces inside the glass building

**Relevant Elements:**

* The glass building's design and layout suggest a modern and open-concept space
* The presence of seating areas and meeting spaces implies a functional purpose, such as an office or educational facility
* The surrounding buildings and trees create a sense of context and environment

**Conclusion:**
Based on the visual information provided, the main subject or scene depicted in this image is likely an office or educational facility, showcasing a modern and functional design.</pre>