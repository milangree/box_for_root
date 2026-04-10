# Box for Root

`Box for Root` 是一个面向 Android Root 环境（Magisk / KernelSU / APatch）的透明代理工具箱模块。

项目深受以下仓库启发并在其基础上持续演进：
- [CHIZI-0618/box4magisk](https://github.com/CHIZI-0618/box4magisk)
- [taamarin/box_for_magisk](https://github.com/taamarin/box_for_magisk)

## 项目定位

本仓库主要提供：
- 统一的代理核心运行管理（mihomo / sing-box / xray / v2fly / hysteria）
- 多网络模式下的透明代理规则编排（TProxy / Redirect / Tun / Mixed / Enhance）
- 订阅、Geo 资源、核心二进制与 WebUI 的统一维护脚本
- 网络监控、CPU监控、定时重启
- 适配 Android Root 生态的模块化目录与服务生命周期管理

## 主要目录

模块工作目录：`/data/adb/box/`

```text
/data/adb/box/
├── bin/                # 代理核心与工具二进制
├── mihomo/             # mihomo 配置目录
├── sing-box/           # sing-box 配置目录
├── xray/               # xray 配置目录
├── v2fly/              # v2fly 配置目录
├── hysteria/           # hysteria 配置目录
├── scripts/            # 核心脚本
│   ├── box.service     # 服务生命周期管理
│   ├── box.iptables    # 透明代理规则管理
│   ├── box.monitor     # 核心监控守护管理
│   └── box.tool        # 更新与维护工具集
├── run/                # 运行时状态与日志
└── settings.ini        # 全局配置文件
```

## 核心脚本

- `box.service`: 启停、重启、状态与定时任务控制；支持 `restart-core` 命令仅重启核心而不影响监控守护。
- `box.iptables`: 透明代理规则启用、重建、清理。
- `box.monitor`: 后台监控守护，支持网络连通性检测、CPU 占用检测、定时重启核心。
- `box.tool`: 订阅更新、Geo 更新、核心更新、配置检查、WebUI 相关维护。

## 文档与社区

- Wiki: <https://github.com/boxproxy/box/wiki>
- 更新日志: [CHANGELOG.md](./CHANGELOG.md)

## 致谢

感谢开源社区与上述项目作者提供的设计思路与实现参考。
