# FEF-Symbols
 A collection of Symbol files for FE-Fates/IF for use with code patching.
using Symbols is a much cleaner way of hooking into code as function names can be referenced instead of just hard offset. A set of symbols for multiple versions of the game also make porting code patches much easier. 

## Disclaimer
Symbols for for US-Birthright is a copy of Conquest.  
The StackTrace files in the korean version of the game were removed so getting symbols can only be done manually from comparing functions from another version of the game to the korean code.

## Using Symbols
rename the symbols file for the version of the game you want to patch to "Symbols.s" and add with your other code files.  

Symbols files can be used in armips by adding  
`.include "Symbols.s"`  
at the top of your .asm patch file.

for Magickoop the include to relative to project folder not the soruce file so in your source file add.  
`.include "../source/Symbols.s"`  

then you can referance the location of function like debug__Menu__DrawWindow instead of using the exact offset, this even works with adding so you can do  Symbol + 0xF to get the offset mid function should you need to patch one instruction.
