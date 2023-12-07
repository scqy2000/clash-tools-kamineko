# 更新 [Clash.Meta 内核](https://github.com/MetaCubeX/Clash.Meta)、[Clash](https://github.com/Dreamacro/clash) dashboard 面板。
# 一、 说明
每天凌晨 0-3 点（北京时间）自动构建生成：
1. Clash.Meta Alpha 版和 Release 版内核
2. Clash dashboard 面板：[Clash 官方面板](https://github.com/Dreamacro/clash-dashboard)、[Razord-meta 面板](https://github.com/MetaCubeX/Razord-meta)、[yacd 面板](https://github.com/haishanh/yacd)、[Yacd-meta 面板](https://github.com/MetaCubeX/Yacd-meta)和 [metacubexd 面板](https://github.com/MetaCubeX/metacubexd)

|面板类型|在线地址|
|-----|-----|
|Clash 官方面板|http://clash.razord.top|
|Razord-meta 面板|http://clash.metacubex.one|
|yacd 面板|http://yacd.haishan.me|
|Yacd-meta 面板|http://yacd.metacubex.one|
|metacubexd 面板|http://d.metacubex.one|


# 二、 使用方法
## 1. 导入内核 Linux 版（以 [ShellClash](https://github.com/juewuy/ShellClash) 导入 Clash.Meta 内核为例）
CPU 架构和内核下载链接后缀对应关系如下：
|CPU 架构|AMD64|ARMv5|ARMv6|ARMv7|ARMv8|mips-softfloat|mipsle-hardfloat|mipsle-softfloat|
|-----|-----|-----|-----|-----|-----|-----|-----|-----|
|**链接后缀**|`amd64`|`armv5`|`armv6`|`armv7`|`armv8`|`mips-softfloat`|`mipsle-hardfloat`|`mipsle-softfloat`|

如 CPU 架构为 ARMv7，则下载链接须修改为：`https://cdn.jsdelivr.net/gh/DustinWin/clash-tools@main/Clash.Meta-release/clash.meta-linux-armv7`
和 `https://cdn.jsdelivr.net/gh/DustinWin/clash-tools@main/Clash.Meta-alpha/clash.meta-linux-armv7`  
连接 SSH 后执行如下命令：
```
# Release 版
curl -o $clashdir/clash -L https://cdn.jsdelivr.net/gh/DustinWin/clash-tools@main/Clash.Meta-release/clash.meta-linux-armv8
# Alpha 版
curl -o $clashdir/clash -L https://cdn.jsdelivr.net/gh/DustinWin/clash-tools@main/Clash.Meta-alpha/clash.meta-linux-armv8
chmod +x $clashdir/clash && $clashdir/start.sh restart
```
## 2. 导入内核 Windows 版（以 [Clash Verge](https://github.com/zzzgydi/clash-verge) 导入 Clash.Meta 内核为例）
编辑文本文档，粘贴如下内容：
```
taskkill /f /t /im "Clash Verge*"
taskkill /f /t /im clash-meta*
# Release 版
curl -o %PROGRAMFILES%\Clash Verge\clash-meta.exe -L https://mirror.ghproxy.com/https://raw.githubusercontent.com/DustinWin/clash-tools/main/Clash.Meta-release/clash.meta-windows-amd64.exe
# Pre-release 版
curl -o %PROGRAMFILES%\Clash Verge\clash-meta.exe -L https://mirror.ghproxy.com/https://raw.githubusercontent.com/DustinWin/clash-tools/main/Clash.Meta-alpha/clash.meta-windows-amd64.exe
```
另存为 .bat 文件，右击并选择以管理员身份运行
## 3. 安装 Clash dashboard 面板（以 ShellClash 安装 metacubexd 面板为例）
Clash dashboard 面板类型和文件名对应关系如下：
|面板类型|文件名|
|-----|-----|
|Clash 官方面板|`clash-dashboard.tar.gz`|
|Razord-meta 面板|`Razord-meta.tar.gz`|
|yacd 面板|`yacd.tar.gz`|
|Yacd-meta 面板|`Yacd-meta.tar.gz`|
|metacubexd 面板|`metacubexd.tar.gz`|

如需要安装 Yacd-meta 面板，则命令中的文件名须修改为 `Yacd-meta.tar.gz` 且下载链接修改为 `https://cdn.jsdelivr.net/gh/DustinWin/clash-tools@main/Clash-dashboard/Yacd-meta.tar.gz`  
连接 SSH 后执行如下命令：
```
curl -o /tmp/metacubexd.tar.gz -L https://cdn.jsdelivr.net/gh/DustinWin/clash-tools@main/Clash-dashboard/metacubexd.tar.gz
mkdir -p $clashdir/ui && tar -zxf /tmp/metacubexd.tar.gz -C $clashdir/ui && rm -f /tmp/metacubexd.tar.gz
$clashdir/start.sh restart
```
