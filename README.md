## Telegram messenger for Android（安卓版 Telegram 通讯软件）

[Telegram](https://telegram.org) 是一款专注于速度与安全的即时通讯应用。它超快、简洁且免费。
本仓库包含 [安卓版 Telegram 应用](https://play.google.com/store/apps/details?id=org.telegram.messenger) 的官方源代码。

## 创建你自己的 Telegram 应用

我们欢迎所有开发者使用我们的 API 和源代码，在我们的平台上创建应用。
目前，我们对**所有开发者**有以下几点要求：

1. 为你的应用 [**申请你自己的 api_id**](https://core.telegram.org/api/obtaining_api_id)。
2. 请**不要**将 Telegram 这个名称用于你的应用——或者务必让你的用户明白它是非官方版本。
3. 请**不要**使用我们的标准 logo（蓝色圆圈中的白色纸飞机）作为你应用的 logo。
3. 请研读我们的 [**安全指南**](https://core.telegram.org/mtproto/security_guidelines)，妥善保护好你用户的数据与隐私。
4. 请记得也要公开发布**你自己的**代码，以遵守相关许可证的规定。

### API 与协议文档

Telegram API 手册：https://core.telegram.org/api

MTproto 协议手册：https://core.telegram.org/mtproto

### 编译指南

**注意**：为了支持 [可复现构建（reproducible builds）](https://core.telegram.org/reproducible-builds)，本仓库包含了占位用的 release.keystore、google-services.json 以及 BuildVars.java 中填好的变量。在发布你自己的 APK 之前，请务必将这些文件全部替换为你自己的。

你需要 Android Studio 3.4、Android NDK rev. 20 以及 Android SDK 8.1。

1. 从 https://github.com/DrKLO/Telegram 下载 Telegram 源代码（git clone https://github.com/DrKLO/Telegram.git）
2. 将你的 release.keystore 复制到 TMessagesProj/config
3. 在 gradle.properties 中填写 RELEASE_KEY_PASSWORD、RELEASE_KEY_ALIAS、RELEASE_STORE_PASSWORD，以便访问你的 release.keystore
4. 前往 https://console.firebase.google.com/ ，创建两个安卓应用，应用 ID 分别为 org.telegram.messenger 和 org.telegram.messenger.beta，开启 firebase messaging 并下载 google-services.json，将其复制到与 TMessagesProj 相同的文件夹中。
5. 在 Studio 中打开该项目（注意是“打开（Open）”，而不是“导入（Import）”）。
6. 填写 TMessagesProj/src/main/java/org/telegram/messenger/BuildVars.java 中的各项值——每个变量旁都有链接，说明在哪里以及获取哪些数据。
7. 现在你可以开始编译 Telegram 了。

### 本地化

我们已将所有翻译迁移至 https://translations.telegram.org/en/android/ 。请使用该平台。
