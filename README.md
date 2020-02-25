# XiaoXinPro-13-2019-hackintosh

## 电脑配置

| 规格     | 详细信息                                                     |
| -------- | :----------------------------------------------------------- |
| 电脑型号 | 联想小新pro13 笔记本电脑                                     |
| 操作系统 | macOS Catalina 10.15.4 beta                                  |
| 处理器   | 英特尔 酷睿 i5 - 10210U                                      |
| 内存     | 16GB板载无法更换                                             |
| 硬盘     | PM981A 更换为EX900 不更换也能安装，见[这里](https://github.com/phenixcxz/xiaoXinPro-i5-PM981) |
| 显卡     | Intel HD Graphics CFL CRB                                    |
| 显示器   | 13.3 英寸 IPS 2560x1600 华星                                 |
| 声卡     | Realtek ALC257                                               |
| 网卡     | 建议更换为 [DW1820A](https://blog.daliansky.net/DW1820A_BCM94350ZAE-driver-inserts-the-correct-posture.html) |

## 已知问题

- `声卡MIC`待解决
- 声卡会周期性掉驱动，就是这次启动驱动成功，下次启动失败，这样往复循环

## 安装部分

详细的安装教程请移步：[联想小新PRO 13 2019兼macOS Catalina安装教程](https://blog.daliansky.net/Lenovo-Xiaoxin-PRO-13-2019-and-macOS-Catalina-Installation-Tutorial.html)

### 安装教程

- `Fn+F2`进入`BIOS`,
- 先查看 `Information`：`Secure Boot` 是否为 `Disabled`;
- 如果 `Secure Boot` 是 `Enabled`，选择左边到 `Security`： 设置 `Secure Boot` 为 `Disabled`;
- `Fn+F10` 保存设置

### 安装后操作

- 安装好系统，先用 `安装的EFI` 进入系统
- 然后找到`终端`执行一下：
- `sudo spctl --master-disable`
- 再执行`重建缓存`:
- `sudo kextcache -i /`
- 替换 `EFI` 或 `config.plist`
- 重启

- ### OC 与 Clover之间切换：

  - 例如Clover 转 OC
  - 先设置OC启动
  - 第一次重启，选择`reset nvram`，这时之前的启动设置会清除了
  - 再次设置对应的`EFI`启动即可

- 镜像下载

  - [[**黑果小兵的部落阁**\] :【黑果小兵】原版镜像](https://blog.daliansky.net/categories/下载/镜像/)

- EFI下载

  - 直接clone即可

- 更新日志

  - [Changelog](Changelog.md)

## 注意

- 安装注意：小新由于安装过程中触摸板可能无法驱动，使用U盘安装macOS会占用仅仅一个USB接口, 建议安装之前先买个usb拓展,用于插入鼠标,来进行安装步骤选项设定

## 正常工作

- 显卡

- 电源

- 蓝牙

- 显示器亮度调节

- 无线（原网卡在macOS 下只能使用蓝牙，建议更换为 [DW1820A ](https://blog.daliansky.net/DW1820A_BCM94350ZAE-driver-inserts-the-correct-posture.html))

- 触摸板 `2-17-2020` （`OC`关闭触摸板方法：`FN+F6` ）

- USB定制（采用 `ACPI` 方式，为使用 `OC` 做准备）

- 声卡

- 其它 `ACPI` 补丁修复采用 `hotpatch` 方式，文件位于 `/CLOVER/ACPI/patched`

## 不正常工作

- ~~睡眠~~ (小新PRO13不能真正睡眠，可以仿真睡眠。唤醒比较困难，`OC` 下唤醒方法是：`电源键`唤醒)
- 声卡MIC

## 功能情况

- CPU变频正常

- 核显驱动正常

- 触摸板驱动正常，支持手势

- 声卡内置MIC无法驱动，其余正常

- FN+F1-F9快捷键正常

- 睡眠耗电测试 每小时`1%~1.2%`（不清后台、不关蓝牙和wifi）

  