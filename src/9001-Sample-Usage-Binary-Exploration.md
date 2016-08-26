# Sample Usage - Binary Exploration

Often, when dealing with software, we might want to take a look
inside the binaries that we build and ship. What symbols are
exported? What code was generated for a function? What relocations
is the linker having to perform? How big are our functions in the
generated code? What data are we loading and which is read-only
and which is writeable?

Currently, on Linux, this means using tools like `nm`, `objdump`,
and others, often with a variety of flags. On Mac OS X, you'll
be looking at `nm` as well as `otool`, again with a variety of
flags.

Our binary exploration tool would build upon the same file objects
used by other modules or extensions within the system by adding
new commands to start with the new functionality.

So, we'll start with a command 'View Symbols' which would do
something like `nm` and show the symbols. Once we're viewing
a list of symbols, we should be able to right click on a
symbol and have a command 'Disassemble' which would be like
running `objdump` or `otool -tV` to view the machine code
for a function.

All of the things that we're discussing here like symbols,
functions, relocation entries, disassembled functions and
the like are all common types whose definition is shared
beyond a single extension. This means that tools like a
debugger or profiler would be able to take advantage of some
of the same capabilities where applicable, such as a fancy
viewer for a disassembled function that shows control
flow graphs, jump visualization and more.
