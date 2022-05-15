# Shell

This project is divided into several subsystems...

Parser: reads a command line and creates a command table. One entry corresponds to a component in the pipeline. divided into a lexical analyzer that separates the input into tokens and a parser that parses the tokens according to a grammar.
The tokens are described in a file shell.l using regular expressions.
The grammar is described in a file shell.y using syntax expressions.
Shell.l is processed with a program called lex that generates a lexical analyzer.
Shell.y is processed with a program called yacc that generates a parser program.

Executor: Creates new process for each entry in the command table. It also creates pipes to communicate the output of one process to the input of the next one and it redirects the stdinput, stdoutput, and stderr

Environment Variables: Set, Print, Expand env vars

Wildcards: Arguments of the form a*a are expanded to all the files that match them.

Subshells: Arguments with ``(backticks) are executed and the output is sent as input to the shell.

