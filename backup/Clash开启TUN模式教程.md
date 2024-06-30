> [!NOTE]
> 对于不遵循系统代理的软件，TUN 模式可以接管其流量并交由 CFW 处理，在 Windows 中，TUN 模式性能比 TAP 模式好
## Windows
- 点击`General`中`Service Mode`右边`Manage`，在打开窗口中安装服务模式，安装完成应用会自动重启，`Service Mode`右边地球图标变为`绿色`即安装成功。
> [!TIP]
> 建议添加`防火墙`规则，如图

![add-firewall-rules](https://github.com/Eray114514/blog.github.io/assets/117504718/39364738-688f-4c0f-b5be-9cee10b99557)
- 点击`General`中`TUN Mode`右边开关启动 TUN 模式。
## MacOS
- ClashX Pro（ClashX不支持，[下载ClashX Pro](https://down.clashcn.com/soft/clashcn.com_ClashXPro.dmg)）的`增强模式`等于TUN模式
- 开启了增强模式则不需要开启系统代理
> 如图，点击`增强模式`，等待至其左边打上“✓”

![4c2c5bb7132e77f843c2be178ca62793c4ed4027_s2_n2_y2](https://github.com/Eray114514/gmeek/assets/117504718/5107816f-d614-4a5f-bc47-5821cd081843)
## Linux
- 点击`General`中`Service Mode`右边`Manage`，在打开窗口中安装服务模式，安装完成应用会自动重启（某些系统需要手动重启 APP），`Service Mode`右边地球图标变为`绿色`即安装成功。
- 点击`General`中`TUN Mode`右边开关启动 TUN 模式。
- 在使用的配置文件中加入如下内容：
    ```yaml
    dns:
      enable: true
      enhanced-mode: fake-ip
      nameserver:
        - 114.114.114.114
    tun:
      enable: true
      stack: system
      dns-hijack:
        - 1.0.0.1:53
    ```
***
> [!NOTE]
> 详细教程：[Clash官方文档-TUN模式](https://doc.clashforwindows.app/tun/)