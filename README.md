# BaymaxTools
Baymax toOls v1.0 beta for x64dbg

Explanation:
Copy the files under the x32\plugins directory to the x64Dbg\x32\plugins directory.
Copy the files under the x64\plugins directory to the x64Dbg\x64\plugins directory.

Introduction:
Extract the signature(pattern) of the selected instruction and check the number of times the signature(pattern) appears in the current search module.

插件介绍：
方便提取所选指令的特征码，及搜索模块内该特征码的出现次数。

使用说明：
将 x32\plugins 目录下的文件复制到 x64Dbg\x32\plugins 目录。
将 x64\plugins 目录下的文件复制到 x64Dbg\x64\plugins 目录。

使用方法：
在反汇编窗口选中多行汇编，右键菜单使用 Baymax ToOls 即可复制特征码或搜索特征码。

00007FFB55651325  | 0F84 93000000                  | je ntdll.7FFB556513BE
00007FFB5565132B  | CC                             | int3
00007FFB5565132C  | E9 8D000000                    | jmp ntdll.7FFB556513BE
00007FFB55651331  | 48:8B4424 40                   | mov rax,qword ptr ss:[rsp+40]
00007FFB55651336  | 44:0970 68                     | or dword ptr ds:[rax+68],r14d
00007FFB5565133A  | 48:8B4424 40                   | mov rax,qword ptr ss:[rsp+40]
00007FFB5565133F  | 48:8B48 30                     | mov rcx,qword ptr ds:[rax+30]
00007FFB55651343  | 48:890D 4E400900               | mov qword ptr ds:[7FFB556E5398],rcx
00007FFB5565134A  | E8 D17AF9FF                    | call ntdll.7FFB555E8E20

Src Hex: 0F 84 93 00 00 00 CC E9 8D 00 00 00 48 8B 44 24 40 44 09 70 68 48 8B 44 24 40 48 8B 48 30 48 89 0D 4E 40 09 00 E8 D1 7A F9 FF
Signature: 0F 84 ?? ?? ?? ?? CC E9 ?? ?? ?? ?? 48 8B 44 24 40 44 09 70 ?? 48 8B 44 24 40 48 8B 48 ?? 48 89 0D ?? ?? ?? ?? E8 ?? ?? ?? ?? 


BTW：
可以在设置选项中勾选需要替换的类型，一般默认选项即可满足。
若复制的特征码在当前模块不唯一，您将看到弹窗提示。
