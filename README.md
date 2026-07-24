# PaperPlane

PaperPlane 是一个开源、自托管的远程 Coding Agent 前端，把飞书、Discord 等协作渠道连接到部署者控制的个人电脑或团队服务器上的 Claude Code、Codex 等 Agent。

## 核心心智模型

```text
Topic / Thread  ↔  PaperPlane Session  ↔  Agent Native Session
   永久一对一          稳定身份               可恢复运行时
```

父聊天是控制面，用于通过 `/new` 显式创建、发现和管理 Session；Topic 或 Thread 是工作面，用于提交任务、查看进度、处理审批、协作以及恢复工作。

## 关键原则

- Topic 或 Thread 就是 Session，不存在普通聊天绑定的降级模型。
- Session 创建后，其渠道地址、Host、Agent、Workspace 和 Owner 保持固定。
- Channel 与 Agent 两侧都可扩展，通过稳定契约和 Capability 协商组合。
- 支持已有本地目录，也支持为 Session 创建独立 Git worktree。
- 权限策略是 Session 的一等属性，包括人工审批和真正跳过审批的 Full Access。
- 群聊中只有明确 `@bot` 的消息才会触发 PaperPlane。
- Session 采用 Owner 与显式 Collaborator 的协作模型。
- Agent 保存完整会话上下文；PaperPlane 只保存路由、权限、生命周期、恢复和审计等控制面状态。
- 渠道断线、daemon 重启或 Agent Runtime 故障不会改变 Session 的身份和原话题地址。
- PaperPlane 可以部署在个人电脑或团队共享服务器，但不提供由 PaperPlane 官方运营的 Agent SaaS。

## 项目蓝图

本仓库只承载 PaperPlane 的产品与架构目标蓝图。

完整内容见 [BLUEPRINT.md](./BLUEPRINT.md)。
