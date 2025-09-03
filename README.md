# 六万脚本 - 武器授权管理系统
## Liuwan Script Studio - Weapon Authorization Management System

 您是否已经受够了玩家不经过管理组私下交易赞助武器而烦躁？是否已经受够了挂哥刷武器到处乱杀？使用此脚本可以最大化的保障服主及玩家的权益，使用我们的武器授权管理系统支持一次性直接永久授权某把武器（实际无上限）的使用权，或者按小时、按天月年租赁赞助枪等、随心所愿，当玩家拿出没有权限的武器时强制收回武器，让ta在获权前无法拿出来。我们的系统还提供多项功能配置供您自由搭配使用，系统内置了Kookbot日志机器人，只需通过修改两行超级简单的代码即可一键接入Kook日志，无需多余操作。特色当没有权限的玩家尝试拿出武器时直接给他塞回兜里让他掏不出来并且立马记录日志方便管理员审查，基本可杜绝玩家私自交易赞助武器及外挂玩家通过触发器等外挂刷取赞助武器等情况。系统已同时支持ESX和QBCore框架，只需在配置文件中指定您服务器使用的框架即可。系统使用了我们精心设计的极致美观大气的用户界面，让您每次打开菜单都有极致的体验感。

---


## 功能

-   **操作简便**: 支持使用指令或快捷键打开管理面板。
-   **选项灵活**: 支持对玩家授予终身权限或自由选择时长（可用于赞助武器租赁）。
-   **日志集成**: 已集成Kookbot日志系统，只需要在 `config` 简单配置两行代码即可高效使用。
-    *日志系统可实时检测无权限玩家非法持有武器情况，可最大化避免玩家私下交易、外挂刷武器等。*
-   **数据库集成**: 通过 `oxmysql` 记录授权信息，保障数据持久化。
-   **框架支持**: 开箱即用，同时支持新版 ESX 和 QBCore 框架。
-   **现代化UI**: 美观大气的用户界面。

## 依赖

-   框架: [ESX](https://github.com/es-extended/es_extended) 或 [QBCore](https://github.com/qbcore-framework/qb-core)
-   [oxmysql](https://github.com/overextended/oxmysql)
-   [ox_lib](https://github.com/overextended/ox_lib)

## 安装步骤

1.  下载 `LiuWan_weaponauth` 插件，并将其放入您服务器的 `resources` 文件夹中。
2.  将 `database.sql` 文件导入到您的数据库中。这会创建一个必需的数据表 (`liuwan_weaponauth`)。
3.  打开 `config.lua` 文件，根据您服务器使用的框架，将 `Config.Framework` 设置为 `'esx'` 或 `'qb'`。
4.  （可选）在 `config.lua` 的 `Config.Kookbot` 表中，根据您的需求开启或关闭Kook日志功能。
5.  在您的 `server.cfg` 文件中添加 `ensure LiuWan_weaponauth`。请确保它在您的框架 (例如 `es_extended`, `qb-core`) 和 `oxmysql` 、`ox_lib` **之后**启动。

## 配置

所有配置都在 `config.lua` 文件中进行。

-   `Config.Framework`: 修改此项为 `'esx'` 或 `'qb'`。
-   `Config.WhitelistedWeapons`: 这个数据表用于列出所有不需要检测的白名单武器，比如系统武器手电筒、电击枪等。
-   `Config.AdminGroups`: 这个表用于配置您服务器的权限组等信息，正常无需修改即可使用。
-   `Config.Messages`: 这个表用于配置插件的文本信息，您可以自由翻译修改。
-   `Config.Kookbot`: 这个表用于控制内置的Kookbot日志系统，分别带有总开关及五个小功能开关。
-    *Token请自行前往Kookapi开放平台申请https://developer.kookapp.cn/app/index*
-    *Channelid请自行使用PC版KOOK开启开发者模式后右键子频道复制ID*
-   `Config.UI`: 用于控制快捷键，设置为false则关闭快捷键，反之则为开启。
-   `Config.DatabaseTable`: 无需设置，如使用正常请勿碰这里！！！

---
