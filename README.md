# 斐讯N1/x86 OpenWRT自用固件自动编译

本项目使用GitHub Actions自动编译斐讯N1（Amlogic S905）/x86的OpenWRT固件。

## 📋 功能特性

### 精简版固件
- ✅ 基础immortalwrt系统
- ✅ 晶晨宝盒
- ✅ 中文界面支持
- ✅ SSH支持
- ✅ 基础网络功能

### 旁路由版本
- ✅ 基础immortalwrt系统
- ✅ 晶晨宝盒
- ✅ IPv6完整支持
- ✅ MosDNS - 高性能DNS解析
- ✅ PassWall - 科学上网工具
- ✅ msd_lite IPTV组播

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

1. 默认IP地址：192.168.2.7
4. 默认用户名：root，默认密码：无（首次登录后请设置密码）

## 🔄 更新说明

固件支持在线升级：
1. 系统 → 晶晨宝盒 → 在线下载更新
2. 系统 → 晶晨宝盒 → 手动上传更新


## 📄 许可证

本项目遵循MIT许可证，详见LICENSE文件。

---

**免责声明**：本固件仅供学习交流使用，使用者需自行承担使用风险。 
