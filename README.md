### sublime配置文件
[使用教程](http://www.cnblogs.com/figure9/p/sublime-text-complete-guide.html)
使用时 使用`git clone` 项目到本地，安装`package control`,`Package Syncing`
配置 `package Syncing`
```json
{
	"sync": true,
	"sync_folder": "D:\\sublime-plugin"
}
```

### 配置右键菜单打开
方法1 下面代码重命名为 sublime_addright.inf,右键安装
```
[Version]
Signature="$Windows NT$"

[DefaultInstall]
AddReg=SublimeText3

[SublimeText3]
hkcr,"*\\shell\\SublimeText3",,,"用 SublimeText3 打开"
hkcr,"*\\shell\\SublimeText3\\command",,,"""%1%\sublime_text.exe"" ""%%1"" %%*"
hkcr,"Directory\shell\SublimeText3",,,"用 SublimeText3 打开"
hkcr,"*\\shell\\SublimeText3","Icon",0x20000,"%1%\sublime_text.exe, 0"
hkcr,"Directory\shell\SublimeText3\command",,,"""%1%\sublime_text.exe"" ""%%1"""
```
方法二 下面代码重命名为 sublime_addright.reg 双击运行,注意修改对应的路径名称
```
Windows Registry Editor Version 5.00
[HKEY_CLASSES_ROOT\*\shell\SublimeText3]
@="用 SublimeText3 打开"
"Icon"="D:\\Program Files\\Sublime Text 3\\sublime_text.exe,0"

[HKEY_CLASSES_ROOT\*\shell\SublimeText3\command]
@="D:\\Program Files\\Sublime Text 3\\sublime_text.exe %1"


[HKEY_CLASSES_ROOT\Directory\shell\SublimeText3]
@="用 SublimeText3 打开"
"Icon"="D:\\Program Files\\Sublime Text 3\\sublime_text.exe,0"

[HKEY_CLASSES_ROOT\Directory\shell\SublimeText3\command]
@="D:\\Program Files\\Sublime Text 3\\sublime_text.exe %1"
```
删除右键打开的脚本
```
Windows Registry Editor Version 5.00
[-HKEY_CLASSES_ROOT\*\shell\SublimeText3]
[-HKEY_CLASSES_ROOT\Directory\shell\SublimeText3]
```