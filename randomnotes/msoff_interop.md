
```python
from timeit import repeat

times = repeat(
    lambda: sum(range(1000)),
    repeat=5,
    number=10000,
)

print(times)


from timeit import timeit

elapsed = timeit(
    lambda: sum(range(1000)),
    number=10000,
)

print(elapsed)
```

```bash
# docx to md
pandoc document.docx -t gfm -o document.md
code document.md
```

```python
from docx import Document
from mi77_utils.interops.msoffice_io import decrypt_msoffice

doc = Document(
    decrypt_msoffice("document.docx")
)

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


from pptx import Presentation
from mi77_utils.interops.msoffice_io import decrypt_msoffice

prs = Presentation(
    decrypt_msoffice("presentation.pptx")
)


for slide in prs.slides:
    for shape in slide.shapes:
        if shape.has_text_frame:
            print(shape.text)
```