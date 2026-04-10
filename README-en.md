# Lenovo SM8750 Kernel Build Project

[简体中文](README.md) | **`English`**<br>

[![GitHub](https://img.shields.io/badge/-GitHub|@qdykernel-181717?logo=github&logoColor=white&style=flat-square)](https://github.com/qdykernel/Build_Lenovo_sm8750)
[![Telegram](https://img.shields.io/badge/Telegram-Channel-blue.svg?logo=telegram)](https://t.me/qdykernel)
[![CoolApk|Profile](https://img.shields.io/badge/CoolApk%7CProfile-3DDC84?style=flat-square&logo=android&logoColor=white)](http://www.coolapk.com/u/1624571)
[![Workflow Status](https://img.shields.io/github/actions/workflow/status/qdykernel/Build_Lenovo_sm8750/build.yml?label=Build&logo=github-actions&style=flat-square)](https://github.com/qdykernel/Build_Lenovo_sm8750/actions)
<br>

---

## 📖 Introduction

This project provides an automated kernel compilation workflow based on **GitHub Actions**, supporting **Lenovo** devices equipped with the **SM8750** platform. Through highly integrated scripts, it enables one-click compilation of GKI kernels featuring **(Re)SukiSU**, **SUSFS**, **ADIOS IOScheduler**, and other functionalities.

### ✨ Key Features

- 🚀 **Fully Automated Compilation** - Based on GitHub Actions, no local environment required
- 🔧 **Multiple KSU Support** - ReSukiSU / SukiSU-Ultra options available
- ⚡ **Performance Optimization** - Integrated ADIOS I/Oscheduler patch
- 💾 **ccache Caching** - Intelligent cache management, 50% speed boost for first compilation with public cache, 80% for subsequent compilations
- 📦 **Ready to Use** - Automatically generates AnyKernel3 flashable packages

---

## 🎯 Quick Start

### Method 1: GitHub Actions Cloud Compilation (Recommended)

#### Step 1. Fork This Repository

Click the **Fork** button in the upper right corner of the repository to copy this repository to your own GitHub account.

#### Step 2. Run Workflow

1. Enter your forked repository
2. Click the **Actions** tab
3. Select the corresponding workflow (see instructions below)
4. Click the **Run workflow** button
5. Fill in the compilation parameters
6. Wait for compilation to complete (first build takes approximately 12 minutes)
7. Download the compiled artifacts from **Artifacts**

### 📋 Available Workflows

| Workflow | Description | Use Case |
|----------|-------------|----------|
| [build.yml](.github/workflows/build.yml) | Full kernel compilation (including KSU/SUSFS, etc.) | Integrate KSU to obtain ROOT |
| [clean-caches.yml](.github/workflows/clean-caches.yml) | Clean ccache cache | When cache is abnormal or recompilation is needed |
| [clear_workflows.yml](.github/workflows/clear_workflows.yml) | Clear workflow run records | Keep Action interface clean |

---

## 🔧 Advanced Features

### Custom Compilation Options

During workflow execution, you can configure the following parameters:

- **kernel_version**: Select the kernel version to compile
- **KSU Type**: Choose KernelSU type (ReSukiSU / SukiSU-Ultra)
- **Enable SUSFS**: Whether to enable SUSFS support
- **Custom Flags**: Add additional compilation flags

#### Using Public Cache

The project will automatically download pre-compiled cache from the public cache repository, allowing acceleration even for the first compilation.

#### Cleaning Old Cache

When build time exceeds 8 minutes, old ccache cache will be automatically cleaned to avoid occupying too much GitHub storage space. You can also manually run the [clean-caches](.github/workflows/clean-caches.yml) workflow to clean all caches.

---

## 🐛 Troubleshooting

### Common Issues

#### 1. Compilation Failure

**Possible Causes**:
- Network issues causing dependency download failures
- Source code conflicts
- Insufficient memory

**Solutions**:
- Check error messages in Actions logs
- Try re-running the workflow
- Clean cache and recompile


### Log Analysis

#### Viewing Compilation Logs

1. Go to the **Actions** page
2. Click on the corresponding workflow run record
3. Expand each step to view detailed output
4. Pay special attention to error steps

#### Key Log Markers

```
[INFO]    - General information
[SUCCESS] - Successfully completed
[ERROR]   - Error (requires immediate attention)
```

---

## 🔗 Related Resources

### Related Projects

- [OnePlus/Realme Kernel Compilation](https://github.com/qdykernel/Build_Oneplus_Realme_Action)
- [SukiSU-Ultra Project](https://github.com/SukiSU-Ultra/SukiSU-Ultra)
- [ReSukiSU Project](https://github.com/ReSukiSU/ReSukiSU)

### Community Support

- **Telegram Channel**: [@qdykernel](https://t.me/qdykernel)
- **CoolApk Profile**: [@qdykernel](http://www.coolapk.com/u/1624571)
- **GitHub Issues**: [Submit Issue](https://github.com/qdykernel/Build_Lenovo_sm8750/issues)

---

## 📜 License

This project is licensed under the **GPL-3.0** License.

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

## 📈 Project Statistics

[![Star History Chart](https://api.star-history.com/svg?repos=qdykernel/Build_Lenovo_sm8750&type=Date)](https://star-history.com/#qdykernel/Build_Lenovo_sm8750&Date)

---

## 📞 Contact

If you have any questions or suggestions, please contact us through the following methods:

- **Telegram**: [@qdykernel](https://t.me/qdykernel)
- **GitHub Issues**: [Create New Issue](https://github.com/qdykernel/Build_Lenovo_sm8750/issues)
- **CoolApk**: DM [@Q1udaoyu](http://www.coolapk.com/u/1624571)

---

**Maintenance Status**: 🟢 Actively Maintained
