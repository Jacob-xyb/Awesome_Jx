# DBI使用教程

## 安装 DBI

1. 下载 [DBI-432](https://store.mzplays.com/archives/32189)
2. 解压后将包里面的 DBI.nro 放到 switch文件夹中

## USB 安装游戏

1. 相册启动 DBI 或 按住 R 键 启动个游戏进入高权限模式后启动 DBI

2. 使用 USB 线链接电脑和 switch

3. 选择 Run MTP responder，按 A 键确认，进入 MTP 模式

   ![](https://store.mzplays.com/wp-content/uploads/2022/11/QQ%E6%88%AA%E5%9B%BE20221101105632-1024x299.png)

4. 稍等片刻，完成加载

   ![](https://store.mzplays.com/wp-content/uploads/2022/11/QQ%E6%88%AA%E5%9B%BE20221101105643-1024x358.png)

5. 此时，电脑中会出现 MTP 设备，如图：

   ![](https://store.mzplays.com/wp-content/uploads/2022/11/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20221101105226.png)

6. 安装游戏到 SD 卡 ，请选择第 `5: MicroSD install`

7. 将待安装的游戏文件，拖拽到 Place NSP, NSZ, XCI or XCZ files here，即可自动安装

   - 这里一定要注意务必等待进度条走完
   - 安装完成后按 B 键 或 X 键 关闭 MTP 模式
   - 返回桌面，安装成功

   ![](https://store.mzplays.com/wp-content/uploads/2022/11/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20221101105342-1024x355.png)

## 卸载补丁、dlc

1. 启动 DBI

2. 进入 Browse installed applications

   ![](https://store.mzplays.com/wp-content/uploads/2022/11/2-1024x280.png)

3. 这里是游戏列表

   ![](https://store.mzplays.com/wp-content/uploads/2022/11/3-1024x222.png)

   ```
   [s|budl]
   ```

   - s 表示有存档，b 表示有本体，u 表示有补丁，d 表示有 dlc，l 表示有 ticket
   - X 键 是选中或取消选中，Y 键 是反选，+ 键 是调出菜单，R 键 是排序，左摇杆按下是运行游戏

4. 按 A 键 ，进入详情，然后选中需要卸载的补丁或者dlc，如下图：

   ![](https://store.mzplays.com/wp-content/uploads/2022/11/4-1024x222.png)

5. 然后按 + 键 调出菜单

   ![](https://store.mzplays.com/wp-content/uploads/2022/11/5-1024x278.png)

   - Delete record 表示删除对应本体、补丁或 dlc
   - Move title to NAND 表示将本体、补丁或 dlc 移动到机身存储
   - Reset required version 表示重置游戏当前系统要求版本
   - Force language 表示强制指定游戏识别的系统语言，默认随系统语言展示游戏界面的可以通过这个选项强制成其他语言
   - Check integrity 表示检查完整性
   - Expose contents via MTP 表示暴露游戏数据（MTP模式可读）

6. 选中 Delete record 后，按 A 键 确认删除

## SD 卡安装游戏

1. 启动 DBI
2. 进入 Browse SD Card
3. 选中需要安装的游戏文件，按 A 键 确认

![](https://store.mzplays.com/wp-content/uploads/2022/11/2-2-1024x276.png)

## 导入导出存档

- MTP 挂载后，直接进入 7: Saves 的文件夹
- installed 里面就是你装的游戏的存档
- 备份或者覆盖文件夹里的内容就是导入导出存档

## 强制设置游戏语言

1. Browse installed applications
2. 找到游戏按 A 键 进入游戏详情
3. 找到游戏本体或补丁按 + 键
4. 选 Force language
5. 选择对应语言后按 A 键 确认
6. 按 B 键 返回到 DBI 主界面
7. 选择 Exit 按 A 键 正常退出 DBI