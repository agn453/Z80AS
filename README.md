# Z80AS
Z80 Assembler compatible with the HiTech C compiler, ZAS assembler and LINK linker

Z80AS is a macro-assembler for Z80 microcomputers, running on the CP/M operating system. 

It runs on Z80-based computers, assembles Z80 source code and is compatible with the HiTech C compiler, ZAS assembler and LINK linker.

It is a major rewrite of the Z80ASM assembler which first appeared on CP/M US User Group, Vol 16. 

The original source was Copyright (C) 1977, Lehman Consulting Services and was put into the public domain. 

It was further modified by Ray Halls in 1982 and Neil Harrison in 1983. 

Last known version was 2.8. It was further modified by Hector Peraza, starting from 2017. 

Z80AS is actually an adaptation of the ZSM4 macro-assembler v4.6 published by Hector Peraza on GitHub ( https://github.com/hperaza/ZSM4 ), made by Ladislau Szilagyi in December 2021 – January 2022.

Thanks to the high quality of the work done by Hector Peraza, the adaptation was easy, actually the most difficult part was writing a new OBJ format object code generator, to obtain compatibility with the HiTech's LINK linker.

Motivation
----------

The main target of the adaptation was to obtain an assembler compatible with ZAS, the assembler that is used by the HiTech C Compiler, but superior as performance. 

The biggest ZAS problem is related to its size (38KB), and because of this ZAS is unable to assemble large source files (too small free space remains for the symbols). 

Z80AS’s size is only 22KB, that means 16KB more memory is available to store the symbols, compared to ZAS.

For example, ZAS fails to assemble the CP/M BDOS source. In contrast, Z80AS succeeds to assemble even a larger file, the CP/M BDOS and BIOS, concatenated.

Often, using HiTech’s C compiler to compile large C files is not possible because ZAS fails to assemble the intermediate file produced by the compiler (“out of memory” error message).

Z80AS is compatible with HiTech’s ZAS and produces object files compatible with HiTech’s LINK linker. 

Therefore, by using the -S option (to output the corresponding assembly file) when compiling a C source file, we can assemble the output with Z80AS, avoiding the “out of memory” error, then we can link the object file with the C library files to obtain the final .COM file.

----------------------------------------------------------------------------------------

Z80AS.HEX is the executable, in .HEX format. Use CP/M's commands LOAD then SAVE to convert-it to Z80AS.com.

Z80AS.HEX was obtained by assembling the Z80AS source files using Z80AS (self assembling assembler :)

The folder SOURCES contains the Z80AS source files, ready to be assembled with ZAS (or Z80AS).

The folder TESTS contains various tests of the Z80AS features.

