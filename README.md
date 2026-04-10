# Lenovo SM8750 内核构建项目

**`简体中文`** | [English](README-en.md)<br>

[![GitHub](https://img.shields.io/badge/-GitHub|@qdykernel-181717?logo=github&logoColor=white&style=flat-square)](https://github.com/qdykernel/Build_Lenovo_sm8750)
[![Telegram](https://img.shields.io/badge/Telegram-频道-blue.svg?logo=telegram)](https://t.me/qdykernel)
[![酷安|主页](https://img.shields.io/badge/酷安|主页-3DDC84?style=flat-square&logo=android&logoColor=white)](http://www.coolapk.com/u/1624571)
[![Workflow Status](https://img.shields.io/github/actions/workflow/status/qdykernel/Build_Lenovo_sm8750/build.yml?label=Build&logo=github-actions&style=flat-square)](https://github.com/qdykernel/Build_Lenovo_sm8750/actions)
<br>

---

## 📖 项目简介

本项目提供基于 **GitHub Actions** 的自动化内核编译工作流，支持 **Lenovo** 搭载 **SM8750** 平台的设备。通过高度集成的脚本，实现一键编译包含 **(Re)SukiSU**、**SUSFS**、**ADIOS调度** 等功能的 GKI 内核。

### ✨ 主要特性

- 🚀 **全自动化编译** - 基于 GitHub Actions，无需本地环境
- 🔧 **多种 KSU 支持** - ReSukiSU / SukiSU-Ultra 可选
- ⚡ **性能优化** - 集成ADIOS I/O调度补丁
- 💾 **ccache 缓存** - 智能缓存管理，首次编译使用公共缓存提速 50%，二次编译提速 80%
- 📦 **开箱即用** - 自动生成 AnyKernel3 刷入包

---

## 🎯 快速开始

### 方式一：GitHub Actions 云编译（推荐）

#### 步骤 1. Fork 本仓库

点击仓库右上角的 **Fork** 按钮，将本仓库复制到你自己的 GitHub 账户。

#### 步骤 2. 运行工作流

1. 进入你 Fork 的仓库
2. 点击 **Actions** 标签页
3. 选择对应的工作流（见下方说明）
4. 点击 **Run workflow** 按钮
5. 填写编译参数
6. 等待编译完成（首次构建约12分钟）
7. 在 **Artifacts** 中下载编译产物

### 📋 可用工作流

| 工作流 | 说明 | 适用场景 |
|--------|------|----------|
| [build.yml](.github/workflows/build.yml) | 完整内核编译（含 KSU/SUSFS 等） | 集成KSU获取ROOT |
| [clean-caches.yml](.github/workflows/clean-caches.yml) | 清理 ccache 缓存 | 缓存异常或需要重新编译时 |
| [clear_workflows.yml](.github/workflows/clear_workflows.yml) | 清理工作流运行记录 | 保证Action界面整洁

---

## 🔧 高级功能

### 自定义编译选项

在工作流运行时，您可以配置以下参数：

- **kernel_version**: 选择要编译的内核版本
- **KSU Type**: 选择 KernelSU 类型 (ReSukiSU / SukiSU-Ultra)
- **Enable SUSFS**: 是否启用 SUSFS 支持
- **Custom Flags**: 添加额外的编译标志

#### 使用公共缓存

项目会自动从公共缓存仓库下载预编译缓存，首次编译也能享受加速效果。

#### 清理旧缓存

当构建时间超过 8 分钟时，会自动清理旧的 ccache 缓存，避免占用过多 GitHub 存储空间。也可手动运行 [clean-caches](.github/workflows/clean-caches.yml) 工作流清理全部缓存。

---

## 🐛 故障排除

### 常见问题

#### 1. 编译失败

**可能原因**:
- 网络问题导致依赖下载失败
- 源代码存在冲突
- 内存不足

**解决方案**:
- 检查 Actions 日志中的错误信息
- 尝试重新运行工作流
- 清理缓存后重新编译


### 日志分析

#### 查看编译日志

1. 进入 **Actions** 页面
2. 点击对应的 workflow 运行记录
3. 展开各个步骤查看详细输出
4. 重点关注报错步骤

#### 关键日志标记

```
[INFO]    - 一般信息
[SUCCESS] - 成功完成
[ERROR]   - 错误（需立即处理）
```

---

## 🔗 相关资源

### 相关项目

- [OnePlus/Realme 内核编译](https://github.com/qdykernel/Build_Oneplus_Realme_Actionl)
- [SukiSU-Ultra 项目](https://github.com/SukiSU-Ultra/SukiSU-Ultra)
- [ReSukiSU 项目](https://github.com/ReSukiSU/ReSukiSU)

### 社区支持

- **Telegram 频道**: [@qdykernel](https://t.me/qdykernel)
- **酷安主页**: [@qdykernel](http://www.coolapk.com/u/1624571)
- **GitHub Issues**: [提交问题](https://github.com/qdykernel/Build_Lenovo_sm8750/issues)

---

## 📜 许可证

本项目采用 **GPL-3.0** 许可证。

```
Copyright (C) 2024 qdykernel

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
```

---

## 📈 项目统计

[![Star History Chart](https://api.star-history.com/svg?repos=qdykernel/Build_Lenovo_sm8750&type=Date)](https://star-history.com/#qdykernel/Build_Lenovo_sm8750&Date)

---

## 📞 联系方式

如有问题或建议，请通过以下方式联系：

- **Telegram**: [@qdykernel](https://t.me/qdykernel)
- **GitHub Issues**: [新建 Issue](https://github.com/qdykernel/Build_Lenovo_sm8750/issues)
- **酷安**: 私信 [@Q1udaoyu](http://www.coolapk.com/u/1624571)

---

**维护状态**: 🟢 活跃维护中
