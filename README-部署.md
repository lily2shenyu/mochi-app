# Mochi 本地 app · 部署说明

这是把「mochi 字卡传讯」网站（https://ling233330-star.github.io/mochi/）打包成安卓 app 的完整工厂。

## 包里有什么

- `www/` —— mochi 的完整网页（index.html 自包含 + manifest + 图标 + sw.js）
- `android/` —— 安卓 WebView 壳（应用名 Mochi，包名 com.lilidreamlove.mochi）
- `.github/workflows/build-apk.yml` —— 自动打包工厂（GitHub Actions）

## 怎么部署（三步）

1. 把这个包里的**所有内容**（www、android、.github 都要，注意 .github 是隐藏文件夹）传到一个 GitHub 仓库的根目录：
   - 建议：你自己的 GitHub（比如 lily2shenyu）新建一个仓库，比如 `mochi-app`，把内容全传进去
2. 等 1~2 分钟，仓库的 Actions 页面会自动开始打包（或手动点「Build APK」按钮）
3. 打包完成后，在 Actions 那个任务里下载 `mochi-apk` 安装包，点开安装（安装时允许「未知来源」）

装好后桌面会出现 Mochi 图标，点开就是完整的字卡传讯 app。

## 说明

- 需要网络：音乐、图片、部分外链功能要联网（网页本身是本地打包的，打开很快）
- 更新：想更新 mochi 时，把新的 index.html 替换 www/index.html 再传回仓库，会自动重新打包
- 键盘、沉浸式全屏都已适配好（键盘弹出自动让位，收起恢复全屏）
- 想改显示名字：改 `android/app/src/main/res/values/strings.xml` 里的 app_name 再构建
