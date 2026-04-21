# OnePlus OP13T KernelSU / KernelSU-Next SUSFS

仅保留 OnePlus OP13T 的内核构建仓库。

## 当前支持范围

- 机型：`OP13T`
- 系统：`OOS16`
- 内核基线：`android15-6.6`
- 打包方式：`AnyKernel3`
- Root 方案：`KernelSU`、`KernelSU-Next`
- 当前默认启用：`HMBIRD`、`BBR`、`TTL`、`Unicode Fix`
- 当前默认关闭：`SUSFS`、`BBG`、`IP Set`、`Droidspaces`、`NTSync`

## 仓库结构

- [build-kernel-release.yml](.github/workflows/build-kernel-release.yml)：GitHub Actions 构建与发布入口
- [action.yml](.github/actions/action.yml)：实际构建复合 Action
- [OP13T.json](configs/oos16/OP13T.json)：OOS16 构建配置
- [oneplus_13t_w.xml](manifests/oos16/oneplus_13t_w.xml)：OOS16 manifest

## 使用说明

1. 在 GitHub Actions 中运行 `Build and Release OnePlus OP13T Kernels`。
2. 按需设置 `KernelSU` / `KernelSU-Next` 分支或提交与编译优化等级。
3. 当前默认配置未启用 `SUSFS`；只有在 [OP13T.json](configs/oos16/OP13T.json) 中重新打开 `susfs` 后，`susfs_branch_or_commit` 输入才会生效。

## 风险说明

- 仅保证面向 OnePlus OP13T 的构建链路。
- 大版本 OTA 后请勿直接沿用旧内核包，除非已重新验证。
- 刷写内核存在变砖风险，请先备份数据并自行评估后果。

## 相关链接

- [兼容性说明](compatibility.md)
- [KernelSU](https://github.com/tiann/KernelSU)
- [KernelSU-Next](https://github.com/KernelSU-Next/KernelSU-Next)
- [SUSFS](https://gitlab.com/simonpunk/susfs4ksu)
