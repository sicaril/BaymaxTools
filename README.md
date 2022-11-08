# BaymaxTools
1. BaymaxTools 是 x64dbg 调试器的一款特征码提取和搜索插件，插件可解析汇编指令并根据用户设置提取特征码；可对进程内存快速搜索特征码条目（是普通内存搜索工具速度的6~10倍）。
2. BaymaxTools is a feature code extraction and search plug-in of x64dbg debugger, plug-in can parse assembly instructions and extract feature code according to user Settings; Feature code entries can be quickly searched for in process memory (6 to 10 times faster than ordinary memory search tools).

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

<img width="458" height="321" src="https://github.com/sicaril/BaymaxTools/blob/master/pic/about.png"/>
<img width="539" height="367" src="https://github.com/sicaril/BaymaxTools/blob/master/pic/search.png"/>
<img width="530" height="305" src="https://github.com/sicaril/BaymaxTools/blob/master/pic/mem_private.png"/>

## BTW:

You can set the replacement type in the settings dialog box, and the general default options are sufficient.
If the copied signature is not unique in the current module, you will see a popup prompt.




