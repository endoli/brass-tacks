# Commands

All interaction with the underlying data and plugins takes place via
commands.

These interactions may happen via a GUI, command line, web interface,
automated processing, chat bots, voice interfaces, VR interfaces,
etc. A command should ideally be able to be flexible about how it
is invoked, so long as it can get the arguments that it needs.

## Self-describing

Commands are required to provide information about their
arguments, help text and more when they are registered
with the system. The information about the arguments would
include the acceptable data-types. The data-type may include
a variety of constraints or restrictions.

## Command Results

When a command is executed in the Unix world, there are only 3 standard
output mechanisms available:

* Standard output
* Standard error
* Exit status

Further, it is up to each command to handle outputting machine
comprehensible representations of its results. Typically,
output is set up for human reading and comprehension.

In our system, this is extensible.

A command has multiple output channels by default, some with
standardized meanings and some that are up to the application
to decide upon.

Like Unix, we would also have standard output and error
channels. These are intended for human consumption.

Further, we would have a data channel. This channel would be
used for conveying a machine-comprehensible representation
of the data resulting from the command. This should obviate
the need for parsing standard output within scripts.

There is also a user-interface channel. This is used by
applications which present some sort of richer UI within
a GUI or TUI or perhaps other sorts of UI interaction systems.
This channel would be interpreted by the UI management system.

## Automation

As all interaction with the systems will be done by executing
commands, it may be possible for software to observe the
commands being executed and common patterns or sequences that
are being repeated. This could allow the system to offer to
automate a repetitive process or suggest better ways of doing
things. (Link from here to the experimental work at Apple in
Hypercard in the early 1990s. Also, beware of the negative
feelings about Microsoft's Clippy.)
