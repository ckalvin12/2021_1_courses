# nasm 參數
```
nasm -h
usage: nasm [-@ response file] [-o outfile] [-f format] [-l listfile]
            [options...] [--] filename
    or nasm -v (or --v) for version info


Response files should contain command line parameters,
one per line.

    -t            assemble in SciTech TASM compatible mode
    -E (or -e)    preprocess only (writes output to stdout by default)
    -a            don't preprocess (assemble only)
    -M            generate Makefile dependencies on stdout
    -MG           d:o, missing files assumed generated
    -MF file      set Makefile dependency file
    -MD file      assemble and generate dependencies
    -MT file      dependency target name
    -MQ file      dependency target name (quoted)
    -MP           emit phony target

    -Zfile        redirect error messages to file
    -s            redirect error messages to stdout

    -g            generate debugging information

    -F format     select a debugging format

    -gformat      same as -g -F format

    -o outfile    write output to an outfile

    -f format     select an output format

    -l listfile   write listing to a listfile

    -Ipath        add a pathname to the include file path
    -Olevel       optimize opcodes, immediates and branch offsets
       -O0        no optimization
       -O1        minimal optimization
       -Ox        multipass optimization (default)
    -Pfile        pre-include a file (also --include)
    -Dmacro[=str] pre-define a macro
    -Umacro       undefine a macro
    -Xformat      specifiy error reporting format (gnu or vc)
    -w+foo        enable warning foo (equiv. -Wfoo)
    -w-foo        disable warning foo (equiv. -Wno-foo)
    -w[+-]error[=foo]
                  promote [specific] warnings to errors
    -h            show invocation summary and exit (also --help)

   --pragma str   pre-executes a specific %pragma
   --before str   add line (usually a preprocessor statement) before the input
   --prefix str   prepend the given string to all the given string
                  to all extern, common and global symbols (also --gprefix)
   --postfix str  append the given string to all the given string
                  to all extern, common and global symbols (also --gpostfix)
   --lprefix str  prepend the given string to all other symbols
   --lpostfix str append the given string to all other symbols
   --keep-all     output files will not be removed even if an error happens
   --limit-X val  set execution limit X
                     passes          total number of passes (default unlimited)
                     stalled-passes  number of passes without forward progress (default 1000)
                     macro-levels    levels of macro expansion (default 1000000)
                     rep             %rep count (default 1000000)
                     eval            expression evaluation descent (default 1000000)
                     lines           total source lines processed (default 2000000000)

Warnings for the -W/-w options:
    other                   any warning not specifially mentioned below (default on)
    macro-params            macro calls with wrong parameter count (default on)
    macro-selfref           cyclic macro references (default off)
    macro-defaults          macros with more default than optional parameters (default on)
    orphan-labels           labels alone on lines without trailing `:' (default on)
    number-overflow         numeric constant does not fit (default on)
    gnu-elf-extensions      using 8- or 16-bit relocation in ELF32, a GNU extension (default off)
    float-overflow          floating point overflow (default on)
    float-denorm            floating point denormal (default off)
    float-underflow         floating point underflow (default off)
    float-toolong           too many digits in floating-point number (default on)
    user                    %warning directives (default on)
    lock                    lock prefix on unlockable instructions (default on)
    hle                     invalid hle prefixes (default on)
    bnd                     invalid bnd prefixes (default on)
    zext-reloc              relocation zero-extended to match output format (default on)
    ptr                     non-NASM keyword used in other assemblers (default on)
    bad-pragma              empty or malformed %pragma (default off)
    unknown-pragma          unknown %pragma facility or directive (default off)
    not-my-pragma           %pragma not applicable to this compilation (default off)
    unknown-warning         unknown warning in -W/-w or warning directive (default off)
    negative-rep            regative %rep count (default on)
    phase                   phase error during stabilization (default off)
    all                     all possible warnings

For a list of valid output formats, use -hf.
For a list of debug formats, use -f <format> -y.
```
