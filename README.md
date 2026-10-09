# 爱心菜单 Android 工程（第一版）

这是一个原生 Android Kotlin 小应用。当前第一版支持在同一台手机上选择菜品、调整数量并生成菜单；尚未实现两部手机的云端同步。

## 最省事的 APK 构建方法（无需在自己的电脑安装 Android Studio）

1. 在 GitHub 创建一个空仓库（Repository）。
2. 将本文件夹中的所有文件上传到仓库，确保 `.github/workflows/build-apk.yml` 也被上传。
3. 打开仓库的 **Actions** 页面，选择 **Build Love Menu APK**，点击 **Run workflow**。
4. 任务完成后打开这次运行记录，在页面底部 **Artifacts** 下载 `LoveMenu-debug-APK`，解压后得到 `app-debug.apk`。
5. 把 APK 传到安卓手机并安装。手机若提示不允许安装此来源的应用，需要在系统设置中允许该文件管理器安装应用。

如果仓库上传后没有看到 Actions，请确认仓库没有禁用 Actions，并且 workflow 文件路径为 `.github/workflows/build-apk.yml`。

## 本地构建

需要 JDK 17、Android SDK 35 和 Gradle 8.9。执行 `gradle assembleDebug`，APK 输出路径为 `app/build/outputs/apk/debug/app-debug.apk`。

## 当前限制

- 这是本地演示版，订单保存在当前应用运行状态中。
- 两部手机暂时不会互相收到订单。后续需要接入云数据库并配置项目凭据，才能实现实时同步。
