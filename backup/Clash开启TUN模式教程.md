对于不遵循系统代理的软件，TUN 模式可以接管其流量并交由 CFW 处理，在 Windows 中，TUN 模式性能比 TAP 模式好
::: warning 注意 近期大部分浏览器默认已经开启“安全 DNS”功能，此功能会影响 TUN 模式劫持 DNS 请求导致反推域名失败，请在浏览器设置中关闭此功能以保证 TUN 模式正常运行 :::
- **Windows**：
    - 点击`General`中`Service Mode`右边`Manage`，在打开窗口中安装服务模式，安装完成应用会自动重启，`Service Mode`右边地球图标变为`绿色`即安装成功。
    - 点击`General`中`TUN Mode`右边开关启动 TUN 模式。
![add-firewall-rules](https://github.com/Eray114514/blog.github.io/assets/117504718/39364738-688f-4c0f-b5be-9cee10b99557)
- **macOS**：
    - 点击`General`中`Service Mode`右边`Manage`，在打开窗口中安装服务模式，安装完成应用会自动重启，`Service Mode`右边地球图标变为`绿色`即安装成功。
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
        - 114.114.114.114
      auto-route: true
      auto-detect-interface: true
    ```
- **Linux**：
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