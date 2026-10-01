# 一加录屏增强（Oplus Recorder Enhancer）

用于增强一加系统录屏的 LSPosed 模块，可自定义录制分辨率比例、帧率和码率。

## 适用范围

- 设备：一加 15
- 系统：Android 16
- 目标应用：`com.oplus.screenrecorder` 版本 `16.4.10_5314b5_260115`

其他设备与版本尚未验证。此前在适配设备上实测过 `1272 × 2772`、`120 FPS` 录制结果；实际效果仍受设备和编码器限制。

## 安装与使用

1. 从 [Releases](../../releases) 下载并安装 APK。
2. 在 LSPosed 中启用模块，为其选择一加屏幕录制应用作用域，重启手机。
3. 首次使用时，通过 root 授予模块保存系统设置所需的权限：

   ```powershell
   & "C:\platform-tools\adb.exe" shell su -c "pm grant dev.rr3.recorder120 android.permission.WRITE_SECURE_SETTINGS"
   ```

4. 打开「一加录屏增强」设置页，选择分辨率与比例，填写帧率和码率，开启自定义参数并保存。从下一段系统录屏开始生效。

设置页底部可隐藏桌面图标。隐藏后可从 LSPosed 的模块设置入口重新打开；如果入口尚未刷新，可运行：

```powershell
& "C:\platform-tools\adb.exe" shell am start -n dev.rr3.recorder120/.SettingsActivity
```

## v0.5.4

首个正式签名发布版本。APK 文件的 SHA-256 见对应 Release 说明。
