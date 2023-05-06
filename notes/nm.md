---
tags: [c]
title: nm
created: '2020-04-24T09:04:34.811Z'
modified: '2023-05-04T13:46:36.709Z'
---

# nm

> list symbols from object files

## option

```sh
-a     # Display all symbol table entries, including those inserted for use by debuggers
-g     # Display only global (external) symbols
-n     # Sort numerically rather than alphabetically
-o     # Prepend file or archive element name to each output line, rather than only once
-p     # Don't sort; display in symbol-table order
-r     # Sort in reverse order
-u     # Display only undefined symbols
-U     # Don't display undefined symbols
-m     # Display the N_SECT type symbols (Mach-O symbols) as (segment_name, section_name) followed by either external or non-external and then the symbol name
-x     # Display the symbol table entry's fields in hexadecimal, along with the name as a string
-j     # Just display the symbol names (no value or type)
-s segname sectname # List only those symbols in the section (segname,sectname).  For llvm-nm(1) this option must be last on the command line, and after the files
-l     # List a pseudo symbol .section_start if no symbol has as its value the starting address of the section, used with the -s option above
-arch arch_type     # Specifies architecture, arch_type, of the file for nm(1) to operate on when the file is a universal file (see arch(3) for the currently known arch_types)
-f  format # for llvm-nm(1) this specifies the output format.  Where format can be bsd, sysv, posix or darwin.
-f     # For nm-classic(1) this displays the symbol table of a dynamic library flat (as one file not separate modules).  This is obsolete and not supported with llvm-nm(1).
-A     # Write the pathname or library name of an object on each line.
-P     # Write information in a portable output format.
-t format # For the -P output, write the numeric value in the specified format. The format shall be dependent on the single character used as the format option-argument:
          # d - value shall be written in decimal (default)
          # o - value shall be written in octal
          # x - value shall be written in hexadecimal
-L     # display the symbols in the bitcode files in the (__LLVM,__bundle) section if present instead of the object's symbol table
```

## usage

```sh
nm main.o

nm -D /lib/x86_64-linux-gnu/libc-2.13.so | grep printf    #  find out what symbols are in a library
```

## see also

- [[c]]
- [[gcc]]
- [[ldd]]
- [[ld]]
