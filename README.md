
# Baymax Tools
BaymaxTools is a feature code extraction and search plug-in for x64dbg debugger. The main functions are:
1. parsing assembly instructions and extracting corresponding feature codes according to user's settings. 2;
2. process memory can be quickly searched for feature code entries (6 to 10 times faster than ordinary memory search tools) ;
3. better parsing of the memory space of the process being debugged (better than x64dbg), including parsing shadowDll, and more convenient memory search by type;
4. support for searching assembly instructions, and compiled instructions can be converted to feature code for searching;
5. support for searching for strings (UNICODE\ASCII\UTF-8);
6. can search for VM-protected instructions;


## Description:

Extract the signature(pattern) of the selected instruction and check the number of times the signature(pattern) appears in the current search module.

## Explanation:

+ Copy the files under the x32\plugins directory to the x64Dbg\x32\plugins directory.
+ Copy the files under the x64\plugins directory to the x64Dbg\x64\plugins directory.

## Instructions:

Select the multi-line assembly in the disassembly window and use Baymax ToOls from the right-click menu to copy the signature or search for the signature.

## Example:

1. 00007FFB5565133F....48:8B48 30...............mov rcx,qword ptr ds:[rax+30]
2. 00007FFB55651343....48:890D 4E400900.........mov qword ptr ds:[7FFB556E5398],rcx
3. 00007FFB5565134A....E8 D17AF9FF..............call ntdll.7FFB555E8E20
4. 00007FFB5565134F....8BD8.....................mov ebx,eax

+ Src Hex: 48 8B 48 30 48 89 0D 4E 40 09 00 E8 D1 7A F9 FF 8B D8
+ Signature: 48 8B 48 ?? 48 89 0D ?? ?? ?? ?? E8 ?? ?? ?? ?? 8B D8 

## Screenshots

<img src="https://github.com/sicaril/BaymaxTools/blob/master/pic/about.png"/>
<img src="https://github.com/sicaril/BaymaxTools/blob/master/pic/search.png"/>
<img src="https://github.com/sicaril/BaymaxTools/blob/master/pic/mem_private.png"/>
<img src="https://github.com/sicaril/BaymaxTools/blob/master/pic/assembly.png"/>
<img src="https://github.com/sicaril/BaymaxTools/blob/master/pic/string.png"/>
<img src="https://github.com/sicaril/BaymaxTools/blob/master/pic/vmcode.png"/>

## BTW:

You can set the replacement type in the settings dialog box, and the general default options are sufficient.
If the copied signature is not unique in the current module, you will see a popup prompt.




