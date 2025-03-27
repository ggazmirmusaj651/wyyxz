# Vultr VPS 修改 root 密码的详细教程（以 CentOS 7 为例）

很多用户在使用 Vultr VPS 时可能会遇到需要修改 root 密码的情况，特别是在快照恢复后。本文将详细介绍如何在 CentOS 7 系统中修改 root 密码。

## 准备工作
- 确保您已登录 Vultr 管理后台
- 准备好新的 root 密码

👉 [【点击查看】2025年最新 Vultr 优惠码及特价云服务器方案汇总](https://bit.ly/VuLtr)

## 详细操作步骤

### 1. 访问 Console
1. 登录 Vultr 管理后台
2. 打开在线 Console
3. 点击右上角的 "Send CtrlAltDel"
4. 按 ESC 键启动 GRUB boot prompt

### 2. 启动 GRUB boot prompt
- 再次点击 "Send CtrlAltDel"
- 按 ESC 键进入 GRUB 引导界面

### 3. 修改启动参数
1. 按 `e` 编辑第一启动项
2. 使用方向键找到以 "linux16" 开头的行
3. 将 `ro` 改为 `rw init=/sysroot/bin/sh`
4. 按 Ctrl + X 或 F10 启动单用户模式

### 4. 修改 root 密码
1. 输入命令：`chroot /sysroot` 进入系统
2. 输入命令：`passwd` 开始修改密码
3. 输入新密码并确认
4. 修改成功后输入：`reboot -f` 重启系统

## 注意事项
- 新密码建议包含大小写字母、数字和特殊字符
- 修改密码后请妥善保管
- 此方法适用于 CentOS 7 系统，其他系统可能略有不同

通过以上步骤，您就可以成功修改 Vultr VPS 的 root 密码了。如果在操作过程中遇到任何问题，可以参考 Vultr 官方文档或寻求技术支持。