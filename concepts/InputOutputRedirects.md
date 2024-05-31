## Input / Output Redirects

### Standard Input (`stdin`)

Has the file descriptor number of 0.

It is used when feeding file contents to a file. For example;

```bash
cat < file.txt
# this is pushing the contents of file.txt into the cat command
```

### Standard Output (`stdout`)

Has the file descriptor number of 1.

The output of a command can be routed to a file with the `>` symbol. To append, use `>>`, using just a single `>` will overwrite the file contents.

### Standard Error (`stderr`)

Has the file descriptor number of 2.

When a command is executed via a keyboard that is considered `stdin`, when the command outputs to the screen that is `stdout`, if the command produced and error that would be considered `stderr`. We can use redirects to route errors from the screen.

For example, the following would not produce any output, instead, the error you would expect to see would be in `error.log`.

```bash
ls -l /root 2> error.log
```