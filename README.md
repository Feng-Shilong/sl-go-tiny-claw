# go-tiny-claw

> 跟着专栏《从 0 开始构建 Agent Harness》动手实现的迷你 Agent 引擎。
> 核心命题：**框架正在坍塌，真正的壁垒下移到 Harness（驾驭工程）**。

把大模型当 CPU、把上下文窗口当内存，Harness 就是为它写的一个微型操作系统——负责调度 Main Loop、回收上下文内存、安全管控极简工具、处理中断与异常。

## 目录结构

```plain
go-tiny-claw/
├── cmd/
│   └── claw/
│       └── main.go          # 程序入口
├── internal/
│   ├── engine/              # MainLoop 核心实现
│   ├── provider/            # 大模型接口抽象与具体厂商 SDK 实现
│   ├── context/             # Token 监控、Prompt 动态组装
│   ├── tools/               # 工具注册表、Middleware、基础极简工具(bash/edit等)
│   ├── memory/              # 基于文件系统的记忆状态存取
│   └── feishu/              # 飞书机器人交互回调
├── go.mod
└── README.md
```

## 快速开始

```bash
go run cmd/claw/main.go
```

预期输出：

```plain
🚀 欢迎来到 go-tiny-claw 引擎启动序列
2026/10/13 19:20:00 架构蓝图搭建完毕，等待各核心模块注入！
```

## 学习进度

- [x] 第一章 01｜架构演进：从 Framework 到 Harness —— 项目骨架
- [ ] 第一章 02｜核心心脏：手写 Agent 的 Main Loop
- [ ] 第一章 03｜慢思考与自省：剥离独立的 Thinking 阶段
- [ ] 第一章 04｜大脑接入：抽象 Provider 接口

## 本地环境

- Go（`brew install go`）
- `GOPROXY=https://goproxy.cn,direct`
