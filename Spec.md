# 安装流程指南
你可能会需要此份指南

## Prepare准备
你可能需要禁用除不必要的内核驱动
<details>
<summary>详情</summary>
保留必要驱动：Lilu , VirtualSMC + 必要扩展驱动 , Whatevergreen , VoodooPS2 
, CtlnaAHCIPort磁盘驱动 （按需要)

禁用其他驱动例如：触摸板，蓝牙等（Kernel -> Add 切换为false)
</details>

```
boot-args: -v dart=0 debug=0x100 ncpi=0x2000 keepsyms=1 -wegnoegpu
```
<details>
<summary>更多</summary>
让设备运行不支持的macOS(高)版本，请使用<code>-no_compat_check</code>
</details>

## 阶段一
*`Install MacOS from External`*: 
在此阶段格式化用于安装的分区为APFS（推荐），并开始安装流程。约16分钟，将自动重启一次。

## 阶段二
*`macOS Installer`*: 
此过程自动进行。约29分钟，可能会重启一次。再次进入，等待安装程序完成，自动重启。
<details>
<summary>有帮助的标识</summary>
再次提到，阶段二可能会重启一次，并且log可见伴随大量复制文件

第二阶段的异常重启可能是正常的，完成了后续工作，所有工作完成，终止标识为
<pre><code>
umount ..... # 此过程卸载已挂载的卷（Volume）

MACH boot
</code></pre>
</details>

两个阶段完成后即可看到macOS入口
