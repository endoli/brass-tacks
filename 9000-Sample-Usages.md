# Sample Usages

## Debuggers and Profilers cooperating

One context might be the "Platform" context. This context
provides ways of interacting with the underlying OS and platform.

For example, this might have a "process manager" that shows the
active processes. Since the means by which data will be
dynamically updated is not yet clear, we'll assume for now that
this is a static list.  The data would be a list of type
`http://workbench.org/Platform/ProcessList`. Each element in the
list would have the type `http://workbench.org/Platform/Process`.
Right clicking on a process object (once it has been displayed)
would tell the front-end to look for any commands that have
requested adding themselves to a context menu on
`http://workbench.org/Platform/Process` objects.  This might
include commands like "Kill" or "Re-nice" at the platform level,
but other contexts could add their own commands here as well.

Suppose that I have a debugger context that works with LLDB to
debug a process. There are multiple ways for this to be
initiated, but one would be to "Attach" the debugger to an object
of type `http://workbench.org/Platform/Process`. If the "Attach" menu
item were selected from the context menu, then the debugger would
be launched and new user interface displayed for the debugger
interface.

While debugging, I might (as I often do) disassemble the current
function. This would result in the display of an object that,
among other things, contains a list of type
`http://workbench.org/AssemblerInstructionList`. This list contains
items of type `http://workbench.org/AssemblerInstruction`.  These
would be displayed on screen and everyone is happy.

However, someone else has written a context that knows about
objects of type `http://workbench.org/AssemblerInstruction`. This
context adds a couple of commands that interact with the
`AssemblerInstruction` objects. One is a context menu item,
"Explain", and when invoked that pops up a small widget that
shows information about the assembler instruction based on the
Intel CPU documentation as well as information from Agner's
optimization website. Other commands might provide hover actions
for a tool tip or other ways of getting information about an
instruction.  This context is written entirely independently of
the debugger context. They integrate with each other by way of
interacting with common object types, like
`http://workbench.org/AssemblerInstruction`.

Someone else has written a profiler context. The profiler can
also (eventually) get down into the assembly code level when
showing information. Fortunately, the profiler was also written
to use the `http://workbench.org/AssemblerInstruction` type for the
instructions, so the reverse engineering context is able to
augment these instructions as shown in the profiler in the same
way that it does with the debugger.
