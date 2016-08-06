# Operating system

Many of the ideas being developed here are just as applicable at the
level of the operating system as they are within particular applications
or frameworks.

Many people who build an OS start at the bottom level. They write a kernel
and they write some drivers and they start building up from there to
the higher levels of the stack.

It is interesting to consider tackling an OS from the opposite direction.
What if you build some libraries and frameworks that work out well for
creating applications, tools and more, but that are also useful as
building blocks for an operating system or an operating environment?

In this way, one can build a new operating system from the top down.
Experiments with the user interface, the data model, what it means
to be an application, how components work together can be done. Later,
we can drop some of the underlying layers in favor of ones that live
on top of a different kernel.

This isn't something to worry about today or even necessarily give
much thought to in any sort of dedicated sense. But it is an interesting
approach to keep open in the backs of our minds!

In particular, it is interesting to watch what happens with Rust
running on the SeL4 kernel as well as projects like Redox. In fact,
projects like Redox may well find some of the data model, approaches
with commands, and more interesting or perhaps even "useful".
