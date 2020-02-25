02-24-2020

- 添加RTC禁止唤醒补丁，解决睡眠耗电过高的问题
- 添加新版whatevergreen、Lilu解决唤醒锁频

#### **以下根据黑果小兵部分作的修改**

02-18-2020

- 触摸板驱动(`02-17`)；
- 关闭触摸板方法 `FN+F6`
- 唤醒方法:`电源键唤醒`
- 优化：`SSDT-I2CxConf.aml`做了较大修改，添加了保护，适用于所有机器

01-29-2020

- 更新OC；
- ALC声卡；

01-08-2020

- 删除VirtualSmc.efi以及config中列表;
- config新增-OSInfo;
- config新增-SignalAppleOS;
- config新增-SupportsCsm;
- config新增-WriteFlash;
- config新增2-AppleSmcIo;
- config新增2-AuthRestart;
- 更新DW1820A蓝牙、Wi-Fi驱动;
- 删除SSDT-Q0CQ0D-Energy.aml;
- SSDT-S1-S3-disable.aml撤回SSDT-S3-disable.aml;
- 删除CPUFriend.kext、CPUFriendDataProvider.kext;
- 添加NVMeFix.kext;
- 更新版本OpenCore.efi版本(https://github.com/n-d-k/OpenCorePkg);
- 删除RU.efi;
- 添加grubwithsetup_var.efi;
- 日常更新Lilu.kext、VirtualSMC.kext等驱动
- 删除modGRUBShell.efi
- config-i5.plist为i5机型使用;
- config-i7.plist为i7机型使用，与i5区别在于DVMT;
- config-识别i7.plist为i7机型使用，在config-i7.plist基础上补充完整信息，取消自动补充参数，识别i7（关于本机）

01-01-2020

- `OC` 暂时不支持引导安装，只驱动集显；

- `OC` 内置 `DW1820A` 蓝牙、Wi-Fi 驱动;

- `OC` 理论上通用 `i5`、`i7` (`i7-10710U` 仿冒 `i5 - 10210U` 的 `CPUID`: `0x0806EC`);

- `OC` 仅添加 `10.15.* `的 `DVMT` 补丁；

  