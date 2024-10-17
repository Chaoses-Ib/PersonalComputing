# QQ
## 聊天记录
Win32:
- [QQBackup/QQDecrypt: 解密并导出 PCQQ / QQ NT 等软件的聊天记录数据库的教程网站](https://github.com/QQBackup/QQDecrypt)
  
  [学习笔记 | QQNT 聊天记录导出](https://blog.reincarnatey.net/2024/0707-qqnt-history-export/)

- [QQBackup/qq-win-db-key: 全平台 QQ 聊天数据库解密](https://github.com/QQBackup/qq-win-db-key)

- [撬开PC QQ的本地SQLite数据库（适用于Msg3.0.db等） - 吾爱破解 - 52pojie.cn](https://www.52pojie.cn/thread-1370802-1-1.html)

- 删除聊天记录不会删除相应图片，也就是说同一个数据库只会越来越大
  - 导出所有消息记录，清空数据库？

    问题是 MHT 是有损导出，如果导出后删除原记录就意味着可能有消息永久丢失了，而不删除又不便于区分是否导出过了。并且退出/解散的群也无法导出消息。

MHT:
- [gyakkun/qq-mht2html: 转换QQ导出的MHT文件到HTML和图片文件, 支持按日期、行数自动分页, 支持多线程, 支持150G+文件](https://github.com/gyakkun/qq-mht2html)
- [Shmily](https://lqzh.me/Shmily/)

  [lqzhgood/Shmily-Get-QQ-PC\_MHT: Shmily-Get-QQ-PC](https://github.com/lqzhgood/Shmily-Get-QQ-PC_MHT)
  - 以下类型不会出现在 QQ 导出的 MHT 文件中
    - 本地图片不存在的不会显示。(空图片占位)
    - 视频不会显示
    - 发送过去的文件消息不会显示(对方接收信息会显示)
    - 自己接收的文件消息不会显示
    - 语音不会显示

  [【开发者自荐】Shmily-聊天记录归档 支持 QQ、Wechat、SMS、Email等 - 发现频道 🔎 - 小众软件官方论坛](https://meta.appinn.net/t/topic/47386)

- [MHT 工具 - 瑞兽谷](https://leorchn.github.io/app/web/mht/)

NT:
- [tjxwork/qq\_db\_export\_group\_image\_path\_and\_move\_or\_delete: QQ数据库导出群图片路径并移动或者删除](https://github.com/tjxwork/qq_db_export_group_image_path_and_move_or_delete)
- [mobyw/GroupChatAnnualReport: 使用 QQNT Windows 聊天记录制作群聊年度报告！](https://github.com/mobyw/GroupChatAnnualReport)
- [ChatPicMigrator4QQNT:  新版QQ PC图片视频消息记录导入](https://github.com/Yana-Hangabina/ChatPicMigrator4QQNT)

  [ChatPicMigrator4QQNT - 新版QQ PC图片视频消息记录文件导入 - 发现频道 🔎 - 小众软件官方论坛](https://meta.appinn.net/t/topic/45899)

- 2024-07 [请问新版QQ怎样导入旧版聊天记录，默认的非常慢，几个小时不到一半 - ＰＣ数码 - Stage1st - stage1/s1 游戏动漫论坛](https://www.saraba1st.com/2b/thread-2191128-1-1.html)
  - > NT刚出的时候直接安装会导入旧版的聊天记录，但是经过实验导入了等于没导入，效果很差。
  - > 草，我就发现QQ又提示版本太低，更新了之后提示可以导入旧的聊天记录，导入之后发现压根没有聊天记录，以前的记录全是其他数据了
- 2024-09 [PCQQ 自动升级 QQNT 消息记录导入失败再重装 PCQQ 丢失聊天记录 - V2EX](https://www.v2ex.com/t/1070691)
- 2024-09 [有没有禁止电脑 QQ 自动升级的办法？ - V2EX](https://www.v2ex.com/t/1073435)

  > 聊天记录不能导出聊天记录备份了，只能同步到另一台设备

Android:
- [Yiyiyimu/QQ-History-Backup: QQ聊天记录备份导出，支持无密钥导出，图片导出。无需编译有GUI界面。Backup Chating History of Instant Messaging QQ.](https://github.com/Yiyiyimu/QQ-History-Backup)

2014-03 [各位是如何处理长达 7/8 年之久的 QQ 聊天记录的？ - V2EX](https://www.v2ex.com/t/106458)