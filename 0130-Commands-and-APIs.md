# Commands and APIs: Oh my!

As programmers, we are used to thinking about systems as existing in
separate and distinct forms at many levels:

* Libraries, functions, APIs.
* Scripting language interfaces.
* Commands for the shell or shell scripts.
* Applications with a GUI.

Your photo library might have a C compatible library for interacting
with it. It might have a Python library as well. Then there might be
a couple of shell commands for working with it. Finally, you have a
GUI application like `Photos.app` or whatever.

Or perhaps you might use Git?  You probably work with it via the
`git` command line utilities. You might use a GUI Git client as well.
You may have used `libgit2` or perhaps one of the Node.js or Python or
Ruby libraries that wrap `libgit2` and make it more friendly in
a scripting environment.

Let's run with the Git example for now!

What if we lived in a different world? One where data is structured
and we have a rich command system?

With the structure of commands in our system, there's no reason that
there can't be a single command implementation for, say, `git log` that
is usable from native code, script, a command line and a graphical client.

The command would have multiple output streams as previously described,
one of which was outputting data in a machine-understandable and typed
form. This can be used by native or script callers. For a command line
or graphical application, the data would be presented using the
"Presentations" features built on top of our UI framework (discussed
later).
