# 在 Mac 上安装 Clash Verge Rev

请只用官方仓库下载，不要用来路不明的网盘或修改过的安装包。

官方发布页：https://github.com/clash-verge-rev/clash-verge-rev/releases

本文写于 2026-11-12。当时最新正式版是 **v2.5.10**。若页面上已经有更新的正式版，请下载最新版，文件名里的版本号会变，芯片对应关系不变。

## 1. 先看清自己的芯片

点左上角苹果菜单 →「关于本机」：

- 写着 **Apple 芯片**（M1 / M2 / M3 / M4 等）→ 下载 `aarch64` 的 dmg
- 写着 **Intel** → 下载 `x64` 的 dmg

也可以在「终端」里输入 `uname -m`：`arm64` 是 Apple 芯片，`x86_64` 是 Intel。

以 v2.5.10 为例，安装包名称是：

- Apple 芯片：`Clash.Verge_2.5.10_aarch64.dmg`
- Intel 芯片：`Clash.Verge_2.5.10_x64.dmg`

这两个名字已在官方 Releases 页面核对。不要下载 Windows 的 `.exe` 或 Linux 的 `.deb` / `.rpm`。

## 2. 安装

1. 打开下载好的 `.dmg`。
2. 把 **Clash Verge** 拖到「应用程序」文件夹。
3. 到「应用程序」里打开它。

## 3. 若提示「已损坏」或无法验证开发者

这是 macOS 的安全拦截，通常不是安装包真的坏了。官方说明的处理方式：

1. 打开「终端」，粘贴下面这一行后回车：

   ```bash
   sudo xattr -r -d com.apple.quarantine /Applications/Clash\ Verge.app
   ```

2. 输入你的 Mac 开机密码（输入时不会显示字符），再回车。
3. 重新打开 Clash Verge。

如果提示「无法验证开发者」，也可以到「系统设置 → 隐私与安全性」页面下部，选择「仍要打开」。

应用名称以「应用程序」文件夹里显示的为准。若文件夹里不叫 `Clash Verge.app`，请把命令里的路径改成实际名称。

## 4. 安装系统服务（开虚拟网卡前必做）

虚拟网卡模式（TUN）需要系统服务。安装一次即可。官方说明见：[常见问题 FAQ](https://github.com/clash-verge-rev/clash-verge-rev/issues/125)。

1. 打开 Clash Verge，进入「设置」。
2. 按官方说明：到 Clash 内核旁边点 ⚙️，再点「授权」。有的版本也会显示「安装服务」，点它即可。
3. 按提示输入 Mac 开机密码，等安装完成。

如果安装失败，可先关掉软件，在终端执行官方发布说明里的重装命令（先卸载再安装）：

```bash
APP="/Applications/Clash Verge.app"
sudo "$APP/Contents/Resources/resources/clash-verge-service-uninstall"
sudo "$APP/Contents/Resources/resources/clash-verge-service-install"
```

命令执行完后重新打开 Clash Verge，再去开「虚拟网卡模式」。开 TUN 是后面必做的一步，系统代理不是必需的。

下一步请看：[导入配置与使用.md](导入配置与使用.md)
