# U盘的格式化

U盘格式化主要有三种方式： FAT32 exFAT NTFS

其中 exFAT NTFS 老旧主板和老旧电脑都无法识别。

`FAT32` 兼容性好，但是有两个缺点，单个分区不能超过32G；单个文件不能超过4G。

# 磁盘分区结构

MBR 和 GPT 分区，GPT比较新，比MBR好。

引导方式也有两种：Legacy 和 UEFI。

Legacy -> MBR （MBR格式）

UEFI -> GPT （GUID格式）

# 微PE辅助安装流程

## 下载安装微PE

[微PE工具箱 - 超好用的装机维护工具 (wepe.com.cn)](https://www.wepe.com.cn/)

## 安装PE到U盘

1. 点击安装到U盘内

   ![image.png](https://s2.loli.net/2023/01/14/lCK4LpIWfk6VYAm.png)

   ![image.png](https://s2.loli.net/2023/01/14/tuJqxUYfBsLTKlr.png)

2. 安装Windows系统

   https://next.itellyou.cn/Original/#

3. BIOS引导，进入PE桌面

4. 磁盘分区

   DiskGenius 分区精灵

   重装系统 右键删除全部分区 -> 保存

   右键转换磁盘为对应格式

   分区时，固态硬盘要勾选4k对齐。

   