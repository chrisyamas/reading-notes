# Read: 02 - The Coder’s Computer

## Notes Outline

#### Choosing A Text Editor

The four most important features that The Older Coder recommends in Choosing A Text Editor are (1) code completion, (2) syntax highlighting, (3) a wide variety or series of themes, and (4) a healthy selection of extensions. Code completion makes you more efficient, while making less mistakes. Syntax highlighting makes text editing easier by colorizing and thereby categorizing the different aspects of your code and content. Having different themes to choose from, and often embracing a dark background with brightly colored text, is beneficial for reducing eye strain and fatigue. A text editor will a number of extensions will allow for more functionality, thereby improving productivity and overall quality of experience.

When it comes to text editors, there are the ones already built into the factory settings of a computer’s software (like “Text Edit” on Mac or “Notepad” on Windows), and then there are third party options (like Notepad++, Text Wrangler, BB Edit, Visual Studio Code, Atom, Brackets, and Sublime Text.

However, there is a difference between Text Editors and Integrated Development Environments (IDEs). While text editors like Text Wrangler do, indeed, “wrangle” text content into a meaningful product, and IDE goes several steps further. An IDE software package–in addition to editing/wrangling text–also manages files, compiles, and debugs. It’s a more comprehensive software tool.


#### Basic Terminal Usage ‘Cheat Sheet’

On a Mac, Terminal is under Applications → Utilities
On Linux, then likely in Applications → System or Applications → Utilities

Most common terminal shell is called bash which stands for Bourne again shell. The command `echo` can be used to display a system variable `$SHELL` stating the current shell.

Shortcut: you can traverse terminal history using the up and down arrows, and edit commands using left and right arrow keys to move cursor.

Commands:
pwd → print working directory
ls → list (do a listing of current, or specified, location)
cd → change directory (if run without arguments, will always return you to home directory)

2 types of paths
absolute paths specify a location (file or directory) in relation to the root directory, they always begin with a forward slash ( / )
relative paths specify a location (file or directory) in relation to where we currently are in the system, and they will not begin with a slash

Tab shortcut: hitting Tab key while typing a path will invoke an autocompletion (or if no result, hitting Tab key again will produce list of possibilities. ex. cd /hTab/<beginning of username>Tab

Some interesting places to look when using cd and ls commands to explore system:
/etc		(this stores config files for the system)
/var/log		(this stores log files for various system programs)
/bin		(the location of several commonly used programs)
/usr/bin		(another location for programs on the system)
