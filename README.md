# ThinkWoCMS · 客户端发行版

外贸独立站建站系统 **ThinkWoCMS** 的客户端安装包分发仓库。

> 本仓库**只存放客户端发行包**，不含开发源码、不含授权服务端（授权站）代码。
# 案例站点

客户案例

> www.jxpmf.com | Quality Custom Parts, Delivered with Precision — From Prototype to Production | JX Manufacturing


## 下载

| 版本 | 文件 | 大小 | 最低 PHP | 说明 |
|---|---|---|---|---|
| v1.0.49 | `ThinkWoCMS-v1.0.49-client.zip` | 9.38 MB | 8.0 | 插件管理区分云端/本地、云端插件授权控制、本地插件后台上传升级 |

历史版本按版本号排列，取最新即可。

> 当前上架包为**明文版**（无需 ionCube Loader，可直接跑，模板可自由修改）。

## 环境要求

| 项 | 要求 |
|---|---|
| PHP | 8.0 / 8.1 / 8.2（按包内版本选择，不同 PHP 大版本不通用） |
| 扩展 | PDO、mbstring、fileinfo、curl、openssl、zip、gd |
| 加密包额外要求 | ionCube Loader（PHP 扩展，装法见下） |
| 数据库 | MySQL 5.7+ / MariaDB 10.3+ |
| Web 服务器 | Nginx 或 Apache，需支持伪静态（ThinkPHP 规则） |

## 安装

1. 解压到站点根目录（保证 `index.php`、`app/`、`public/` 在同一层）
2. 配置站点根目录指向站点根（**不是** `public/`）
3. 浏览器访问站点，按向导填数据库信息，自动建表
4. 后台 `/admin.php` 登录，进「站点设置 → 授权」填授权码与授权站地址

## 升级

后台 →「系统更新」→ 检查更新 → 一键升级（自动备份、冲突文件不覆盖）。

- **加密包**客户升级到含新加密文件的版本后，服务器必须已启用 ionCube Loader，否则站点会报
  `encoded file requires the ionCube PHP Loader`。升级前请先确认 Loader 已装好。
- 宝塔面板：软件商店 → PHP 设置 → 安装扩展 → ionCube → 重启 PHP

## 授权说明

- 授权码与绑定域名一一对应，换域名需在授权站改绑
- 授权失效**不锁站**：站点照常运行，只限制在线更新与部分云端插件
- 云端插件由授权站下发，需授权站开通并在有效期内方可启用
