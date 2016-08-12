# Markup

Many tools and applications output text. In some, this is going
to a terminal. In others, it is being displayed within the
application. In still others, it is being rendered to HTML and
displayed by a browser.

Another big use of text is for actual written material like
books, papers, and other artifacts.

In all of these scenarios, we would like to be able to:

* Maintain formatting that is correct for the target
  device. This formatting includes color and style
  just as much as control over structure and layout
  in lists, columns, tables, etc.
* Have the same text be output to multiple targets,
  with it appearing correctly on all of them.
* Associate additional information with spans of
  text. This means that it should be possible to
  access the original underlying object that generated
  some text, when appropriate.
* Remember the higher level meaning associated with
  data that is being represented by the text. When we're
  rendering a math equation, it would be nice to keep
  in mind that it is math and deserves specialized
  structure in the markup, not just treated as a
  bunch of layout directives.

This has some obvious relationships with our approach to
structured data.

A "subject" from our data stores can be associated with text.
This provides access to all of the other information about
the "subject".

## Approach

### Markdown?

Markdown doesn't work for us here as it is a very limited
form of markup and doesn't support a very rich model in
the backend. That said, markdown syntax can be used to
drive some aspects of the system.

### Concrete Syntax

For now, I don't care about the concrete syntax at all. My
view of the `markup` library is that it will be the data
structures and rendering implementations for a variety of
output formats or devices.

### Document Tree (Document Graph)

Many tools for dealing with text formatting and markup
languages maintain a document tree to represent the
structured document. This is true of many Markdown
processing tools as well as tools like Python's
docutils (used for ReStructuredText), asciidoctor,
and Pandoc.

We should be able to borrow heavily from the design
of these existing systems.

Also, this is really a graph, not a tree, due to things
like linking to the underlying objects being presented
as well as stylesheets and the like.

### GUI Widget Graphs

There's an interesting overlap between the document graph for
displaying information and the UI graph that is used for
displaying the user interface. Should there be 2 distinct
solutions here?
