# Graphs as the Primitive

In Unix, a sequence of bytes is typically seen as the primitive
for all data interchange. Files are sequences of bytes. Pipes
are sequences of bytes. Standard input and output are sequences
of bytes.

In our systems here, we are going to have 2 primitives that
everything else will build upon.

The first is the graph. This is not a graph in the sense of
x and y axes and plotting lines or bars to make charts. No,
here we are talking about graphs from the field of knowledge
representation, also known as semantic networks or semantic
graphs.

A [semantic network](https://en.wikipedia.org/wiki/Semantic_network):

    ... represents semantic relations between concepts.
    This is often used as a form of knowledge representation.
    It is a directed or undirected graph consisting of vertices,
    which represent concepts, and edges, which represent semantic
    relations between concepts.

Graphs allow us to describe the underlying objects in ways
that are machine understandable and we can build many things
on top of these graphs.

We will cover this in more detail in an upcoming section
on Structured Data (yet to be written).
