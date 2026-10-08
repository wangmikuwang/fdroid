# 文游 F-Droid 仓库

[虹叙](https://github.com/wangmikuwang/WenYou-TextQuest)与[星叙](https://github.com/wangmikuwang/WenYou-TextQuest-Beta)的自建 F-Droid 仓库。

## 添加仓库

- 在手机上打开 **https://wangmikuwang.github.io/fdroid/** 一键添加；或
- F-Droid → 设置 → 仓库 → 「+」，填入 `https://wangmikuwang.github.io/fdroid/repo`

仓库指纹（SHA-256）：

```
885F92BA3C2DDD5EE6F095BB3E6796A194E4EE88F558FB95FCB4C18388A5B9E6
```

安装包与 GitHub Releases 的正式版相同、签名一致，可与应用内更新互相覆盖升级。

## 工作方式

[`update.yml`](.github/workflows/update.yml) 每天运行一次（也可手动运行）：下载两款应用的最新正式版 APK，用 fdroidserver 按 [`config.yml`](config.yml) 与 [`metadata/`](metadata/) 生成并签名索引，发布到 GitHub Pages。签名密钥只保存在仓库 Secrets（`FDROID_KEYSTORE`、`FDROID_KEYSTORE_PASS`）中。
