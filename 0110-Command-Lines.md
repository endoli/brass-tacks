# Command Line Interfaces

Unlike modern graphical user interfaces, some systems from the olden
days had a command line as part of the graphical interface. This is not
like having `Terminal.app` on macOS or a DOS prompt on Windows.

The command line in these old systems wasn't limited to text output,
nor was it necessarily separate from the running applications. Much
like in emacs, it was part of interacting with the system. It was an
alternate way to signify your intent, much the same as pressing a button
or selecting a menu item.

Some recent text editors have a command palette, such as Sublime Text,
Atom and Visual Studio Code. This is a similar idea in that it is
intended to make the interface more immediate and accessible for
someone that is comfortable and familiar with their tools.

## Autocomplete

...

## Typed Completion History

Since we have a system that is heavily based upon structured data, we
have the possibility for some extensions to things that people expect.

Many command line systems maintain a history of the previous commands
and the ability to execute commands again.  Our command line will be
able to have a history of arguments and do type-aware completion
history.

For example, you are in a command shell and run the command `make-directory`
to create a new directory `abcdef`. This inserts an entry in the history
of recent items interacted with for that directory, with the awareness
that it is a `directory` object. You now want to `change-directory` to
that directory. This prompts you to autocomplete, looking for a `directory`
object. The system should be able to identify likely directory objects
from your environment (current directory, etc), but also from the history
of recent items as well.
