# md-blogger
md-blogger turns organized markdown files into a website.

## Dependencies
- **markdown**, to convert markdown pages into html.
- **lxml**, to make the html just a little bit prettier.

## Setup
md-blogger requires a very specific structure for organization.

### ./build
The python script, ```main.py```, should be in this folder along with the other
required build files.

#### categories.json
- Provide a map in the file with the key being the folder name without "-md"
appended, and the value being what the section will be labeled as in the index.

Have the value be a two element object if you wish to include a section/header description.

#### index.html
- Provide a header and a closer for the index page before the footer is placed.
- You can indicate to include the css file in the header.
- [REPLACE] indicates where the converted markdown should be placed in the
generated html.

#### index_footer.md
- Provide a footer in markdown to be appended to the index page.

#### template.html
- Provide a header and a closer for a reference page before the footer is placed.
- You can indicate to include the css file in the header; remember the folder
structure must have ".." preceding.
- [REPLACE] indicates where the converted markdown should be placed in the
generated html.

#### page_footer.md
- Provide a footer in markdown to be appended to a reference page.

#### style.css
- Provide a css file to be copied over.

### General notes
- Clean builds are always done. ```./out``` is deleted every time the script is ran.
- If access is denied, just rerun the script.
- Markdown pages should be created with the ```../img``` path for images.
- For footers to be placed properly with a separated line, reference pages
should have 2 newlines at the end of each file.
- Each reference page will only use its file name to know where to be placed. It
will be labeled as the page's markdown header, indicated by a #, in the index
page.
- Each reference is indexed by alpha due to how files are organized on operating
systems; however, an included text file in the -md directory called
```order.txt``` can be specified to establish a specific order for the files to
be indexed.
- The final version is created in ```./out```
