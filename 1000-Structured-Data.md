# Structured Data

## Graphs as the Primitive

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

The second primitive that we will build everything upon
is very closely related to graphs. It is the sequence of
operations used to update a graph. Many of our systems build
not just upon using graphs, but upon keeping graphs in sync
or up to date.

## Constraining Data Shapes

In the web world, [GraphQL](http://graphql.org/) is being
used to constrain the shape of a graph that is returned
from a query. This is used so that the caller of a service
can let the service know precisely which fields of data
are required, allowing the service to avoid the production
of data that won't be used.

In the RDF world, there is a technology that might be
usable as a similar mechanism:  [SHACL](https://www.w3.org/TR/shacl/).

There are many scenarios where it may be useful to
supply a data shape to something that will generate data
rather than apply a filter after the fact. In generating
a list of files, there are many attributes which may be of
interest to some, but which are expensive to calculate,
like running `magic` on a file to sniff out what type of
file it might be. When getting a list of processes, some
callers might want to know what sockets or file handles
are opened by a process or such details as what memory
mappings have been established. As these things can be
expensive, but are of interest to some, but not all,
callers, having the ability for the caller to establish
the shape of the data that it wants is useful.

By doing this, we will be able to have an easier set
of APIs to deal with: "Process Info" can get us any
information about processes rather than having a basic
"Process Info" and then additional APIs for getting
more esoteric information (like the memory mappings).

## Searching, Sorting, Filtering

Performing search, sorting and filtering operations on
unstructured data isn't ideal. Since we have structured
data and have information about the data types involved,
we can do significantly better.

Many small graphs can be operated upon without complicated
indexing or anything else. However, larger graphs or more
persistent graphs may want to set up advanced indexing as
an optimization.

Lucene provides some good background for what sort of
indexing might be useful. For example, value range indexing
as well as full text search techniques would both be
useful.
