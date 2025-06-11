# 斐讯N1 OpenWRT固件自动编译

本项目使用GitHub Actions自动编译斐讯N1（Amlogic S905）的OpenWRT固件。

## 📋 功能特性

### 精简版固件
- ✅ 基础OpenWRT系统
- ✅ 晶晨宝盒（luci-app-amlogic）- 支持在线升级
- ✅ 中文界面支持
- ✅ SSH支持
- ✅ 基础网络功能
- ❌ 不包含任何其他插件

### 旁路由版本
- ✅ 基础OpenWRT系统
- ✅ 晶晨宝盒（luci-app-amlogic）
- ✅ IPv6完整支持
- ✅ MosDNS - 高性能DNS解析
- ✅ PassWall - 科学上网工具
- ✅ 中文界面支持

## 🚀 使用方法

### 1. Fork本仓库
点击右上角的`Fork`按钮，将此仓库fork到你的GitHub账户。

### 2. 启用GitHub Actions
1. 进入你fork的仓库
2. 点击`Actions`选项卡
3. 点击`I understand my workflows, enable them`启用Actions

### 3. 开始编译
#### 方法一：手动触发
1. 点击`Actions`选项卡
2. 选择`编译斐讯N1 OpenWRT固件`
3. 点击`Run workflow`
4. 选择要编译的版本（精简版/旁路由版本）
5. 点击`Run workflow`开始编译

#### 方法二：修改代码自动触发
修改任何文件并push到仓库，Actions会自动开始编译。

### 4. 下载固件
编译完成后，固件将上传到：
- **Artifacts**：在Actions页面的编译记录中下载
- **Releases**：在仓库的Releases页面下载

## 📁 文件结构

```
├── .github/workflows/
│   └── build-n1-openwrt.yml    # GitHub Actions工作流
├── configs/
│   ├── n1-minimal.config       # 精简版配置
│   └── n1-bypass.config        # 旁路由版配置
├── scripts/
│   ├── diy-part1.sh            # 自定义feeds脚本
│   └── diy-part2.sh            # 自定义配置脚本
└── README.md
```

## ⚙️ 自定义配置

### 修改默认设置
编辑`scripts/diy-part2.sh`可以修改：
- 默认IP地址
- 主机名
- 时区设置
- 默认密码等

### 添加/删除软件包
编辑对应的配置文件：
- `configs/n1-minimal.config` - 精简版
- `configs/n1-bypass.config` - 旁路由版本

### 添加新的feeds源
编辑`scripts/diy-part1.sh`添加新的软件源。

## 🔧 编译依赖

本项目基于以下开源项目：
- [ImmortalWrt](https://github.com/immortalwrt/immortalwrt) - 源码仓库
- [unifreq/openwrt_packit](https://github.com/unifreq/openwrt_packit) - 打包工具
- [ophub/luci-app-amlogic](https://github.com/ophub/luci-app-amlogic) - 晶晨宝盒

## 📖 安装说明

1. 下载编译好的固件（.img文件）
2. 使用balenaEtcher、Rufus等工具将固件写入U盘
3. 斐讯N1插入U盘，从U盘启动
4. 使用晶晨宝盒功能安装到内置存储

## ⚠️ 注意事项

1. 首次使用建议选择精简版，确认硬件兼容性
2. 旁路由版本体积较大，包含较多网络工具
3. 默认IP地址：192.168.1.1
4. 默认用户名：root，默认密码：无（首次登录后请设置密码）

## 🔄 更新说明

固件支持在线升级：
1. 系统 → 晶晨宝盒 → 在线下载更新
2. 系统 → 晶晨宝盒 → 手动上传更新

## 📞 技术支持

如遇问题，请：
1. 查看Actions编译日志
2. 提交Issue说明问题
3. 参考[恩山论坛](https://www.right.com.cn/forum/)相关帖子

## 📄 许可证

本项目遵循MIT许可证，详见LICENSE文件。

---

**免责声明**：本固件仅供学习交流使用，使用者需自行承担使用风险。 