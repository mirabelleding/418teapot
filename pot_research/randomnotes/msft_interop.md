```bash
# docx to md
pandoc document.docx -t gfm -o document.md
code document.md
```

```python
# !pip install python-docx
from docx import Document

doc = Document("document.docx")

# inspect document
doc.paragraphs
doc.tables
doc.sections
doc.styles

# extract text
text = "\n\n".join(
    paragraph.text
    for paragraph in doc.paragraphs
)
```

```python
# !pip install python-pptx
from pptx import Presentation

prs = Presentation("presentation.pptx")


for slide in prs.slides:
    for shape in slide.shapes:
        if shape.has_text_frame:
            print(shape.text)
```