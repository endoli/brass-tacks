# Workbench

Workbench is an application that provides a user interface for
interacting with a set of tools.  The tools are run as plugins
and will typically perform their work in a separate process,
communicating with the front-end via a simple protocol.

## Motivation

Workbench is intended to create tools that can integrate and
collaborate with each other rather than a distinct set of
entirely separate applications. Workbench learns from how
tools worked on the Lisp machines from Symbolics, the Oberon
environment from ETHZ, Smalltalk and other environments that
focused heavily on integration, interactivity and productivity.

Additionally, Workbench should make tools and capabilities
more discoverable. Many people are not aware of all of the
tools available to them, how to use them, or how to integrate
those tools with their workflow. There is significant room
for improvement in this area.

Workbench is not intended to be a fully general purpose user
interface toolkit at this point in time, but is focusing on
certain types of tools. The scope of the Workbench capabilities
may grow in the future, once we have a better idea of how things
can, should, and might work.
