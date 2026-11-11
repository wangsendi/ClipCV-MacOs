# ClipCV

[下载最新版本](https://github.com/wangsendi/ClipCV-MacOs/releases/latest/download/ClipCV.dmg)

发布新版时，先在 Xcode 设置 Version，再创建 GitHub Release，上传 `ClipCV.dmg` 后点击 Publish release。GitHub Actions 会从安装包读取版本和系统要求，生成签名并自动提交 `appcast.xml`，无需手改这个文件。

应用的 Build 应跟随 Version，并随每次发布递增。签名密钥保存在仓库的 `SPARKLE_PRIVATE_KEY` Actions secret 中。

自动更新使用每个 Release 的固定下载地址，保证缓存的 appcast 与安装包签名对应。上方普通下载链接始终指向 latest。

替换已经发布的安装包后，可手动运行 Actions → Update appcast → Run workflow 刷新更新源。
