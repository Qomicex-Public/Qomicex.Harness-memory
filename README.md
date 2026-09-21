# Qomicex.Harness-memory

记忆插件的模型分发仓库。只放 release 资产，不放源码——源码在
[Qomicex.Harness](https://github.com/Qomicex-Public/Qomicex.Harness)。

## 为什么单独一个仓库

微调后的判断模型是 278 MB 的二进制，放进源码仓库会让每次克隆都变慢，
且没法做版本化管理。放在 release 资产里可以按 tag 寻址、可校验、可回滚。

## 当前资产

| 文件 | 大小 | 用途 |
|---|---|---|
| `functiongemma-judge-q8_0.gguf` | 278.1 MB | 记忆判断层的本地模型 |

SHA256: `af24b58feb6efc3846f07e991051ee599f284f41a2745539783728a5f4eaedac`

模型来源：`google/functiongemma-270m-it` 经 LoRA 微调
（daq 数据来自 opencode 真实会话 731 条），合并权重后由 llama.cpp
转 GGUF 并量化为 Q8_0。

## 下载

源码里通过 ghproxy 代理从 GitHub release 下载，避免国内直连
huggingface/giithub 的速度问题。
