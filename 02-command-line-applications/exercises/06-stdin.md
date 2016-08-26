# stdin

Todo: Unix philosophy

Todo: [TTY](https://en.wikipedia.org/wiki/Teleprinter)
[Node.js TTY](https://nodejs.org/api/tty.html#tty_tty)

## Requirements

Use a unix pipe to pass text a Node.js program. Simply print "Piped text: "
followed by the piped text. If no text was piped, print "No piped text."

Expected:

```bash
$ node stdin.js
No piped text.
$ echo 'Hello World' | node stdin.js
Piped text: Hello World
$ echo pwd | node stdin.js
Piped text: /Users/scott/workspace/node-milestones/02-command-line-applications/solutions
```
