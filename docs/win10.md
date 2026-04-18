# windows10限制更新

https://blog.csdn.net/qq_62649745/article/details/145519980

## 修改注册表

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsUpdate\UX\Settings

右键 Setting 这个项目然后新建，创建一个 DWORD（32 位）值，将其命名为`FlightSettingsMaxPauseDays`，然后将基数改为十进制，选择自己想要设置的最大暂停更新的天数即可
