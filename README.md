# fbopt

A template for option parsing in Bash based on getopt

## Version

0.4.2

## Reasons

See https://frnmst.gitlab.io/notes/my-bash-option-parsing-template.html#reason

## Usage

You can adapt and include the template as a separate part of your
program by using `source ./fbopt` or `. ./fbopt` from the main
script.

To allow inclusion in any project the template and its documentation is 
released under the CC0 1.0 license.

## Bashisms

[Bashisms](https://mywiki.wooledge.org/Bashism) are Bash specific syntax
elements. I decided to use these because of programming convenience rather than 
compliancy. 

You will find at least the following bashisms in the template

| Bashism | Example |
|---------|---------|
| local variables | `local variable='value'` |
| arrays | `"${array[@]}"` |
| indirect variables | `"${!variable}"` |

## Conventions

The following elements should be common sense and not be specific to fbopt

| Convention | Notes | Examples |
|------------|-------|----------|
| all constants are enclosed within single quotes | elements within single quotes (only) are not interpreted by the shell | `'constant'` or `'this is a constant'` |
| some variables are enclosed within double quotes | double quotes serve as a delimiter between multiple variable names if these are consecutive. Every variable between the quotes is interpolated | `"${variable}"` |
| some variables are not enclosed within double quotes | the only variables allowed without double quotes are integers (such as return values) and loop iterators (because these won't work otherwise) | `${?}` or `for v in ${values}; do echo "${v}"; done` |
| all variables use the curly braces notation | curly braces serve as a delimiter between multiple variable names if these are consecutive | `"${variable}"` or `${variable}` |
| all variable names with a constant value must be capital case | you might want to load some constants from a configuration file to override the values of options within the fbopt file | `local flag_a="${FLAG_A_DEFAULT_VALUE}"` | 

## Dependencies

The template is known to work with the the packages listed here. These must be 
of course installed on your system.

| Package | Executable | Version command | Package Version |
|---------|------------|-----------------|-----------------|
| [GNU Bash](http://www.gnu.org/software/bash/bash.html) | `/bin/bash` | `$ bash --version` | `GNU bash, version 4.4.23(1)-release (x86_64-unknown-linux-gnu)` |
| [util-linux](https://www.kernel.org/pub/linux/utils/util-linux/) | `/bin/getopt` | `$ getopt --version` | `getopt from util-linux 2.33` |

NOTE: this documentation always refers to the latest [fbopt release](https://github.com/frnmst/fbopt/releases).

## Software using fbopt

- [mcmc-comparisons](https://github.com/frnmst/mcmc-comparisons)
- [spectrscan](https://github.com/frnmst/spectrscan)
- [get-fattura-pa](https://github.com/frnmst/get-fattura-pa)

## Resources

- https://www.mariusvw.com/2013/02/24/bash-getopt-versus-getopts/
- http://abhipandey.com/2016/03/getopt-vs-getopts/
- https://unix.stackexchange.com/questions/62950/getopt-getopts-or-manual-parsing-what-to-use-when-i-want-to-support-both-shor

## License

Written in 2018 by Franco Masotti/frnmst <franco.masotti@live.com>

To the extent possible under law, the author(s) have dedicated all 
copyright and related and neighboring rights to this software to the public 
domain worldwide. This software is distributed without any warranty.

You should have received a copy of the CC0 Public Domain Dedication along 
with this software. If not, see 
<http://creativecommons.org/publicdomain/zero/1.0/>. 
