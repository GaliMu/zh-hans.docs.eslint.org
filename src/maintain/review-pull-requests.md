---
title: 拉取请求审查
eleventyNavigation:
    key: reviewing pull requests
    parent: maintainer guide 
    title: 拉取请求审查
    order: 2

---

经常会有人提交拉取请求，它代表了我们与社区互动的最佳机会。因此在合并前，审查拉取请求并积极就此请求进行讨论，非常重要。

## 谁可以审查拉取请求？

所有人（包括团队成员和公众）都可以在拉取请求上留下评论。

## 审查拉取请求

当有新的拉取请求时，机器人会检查以下内容：

1. 提交者是否签署了 CLA？
1. 提交消息摘要的格式是否正确？
1. 提交摘要是否太长？

机器人会发布评论并说明它发现的问题。在这些问题得到解决之前，你不用再看该拉取请求（也无需在拉取请求上发表评论，要求提交者按照机器人的要求去做——这就是为什么我们有机器人！）。

当机器人检查无误后，你需要检查以下内容：

1. 仔细检查提交信息标签（“Fix:”、“New:”等）是否基于问题而进行修正（如果没有引用问题，则基于所述问题）。
1. 如果拉取请求对核心进行了修改，确保存在一个问题，并且拉取请求在提交消息中引用了该问题。
1. 代码是否遵循了我们的约定（包括头文件注释、JSDoc 注释等）？如果没有，请留下反馈并参考惯例文件。
1. 对于代码的修改。
    * 是否有测试来验证这个改动？如果没有，请要求他们提供。
    * 是否需要为该修改提供文档？如果是，请让提交者知道。
1. 是否有自动测试的错误？如果有，请让提交者检查一下。
1. 如果你已经审查了该拉取请求，并且没有悬而未决的问题，请留下评论“LGTM”以表示你的批准。如果你想让其他人来验证该修改，请评论“LGTM，但我想让其他人进行二次验证”。

**注意**：如果你是团队成员，并拉取请求上留下了评论，请跟进以验证你的评论是否得到了处理。

## 谁可以合并拉取请求？

TSC 成员、审查员、提交者和网站团队成员可以合并拉取请求，这取决于拉取请求的内容。

网站团队成员可以合并 `eslint.org` 仓库中以下几种情况的拉取请求：

1. 文档修改
1. 依赖升级
1. 杂事

提交者可以合并以下几种情况的非破坏性拉取请求：

1. 文档变更
1. 错误修复（针对规则或核心）
1. 依赖升级
1. 与构建工具有关
1. 杂事

此外，若拉取请求已获 TSC 成员批准，则提交者可以合并任一非破坏性拉取请求。

TSC 成员可以合并所有拉取请求，包括提交者也可以合并的请求。

## 何时合并拉取请求

我们使用“合并（Merge）”按钮将请求合并到仓库中。在合并拉取请求前，需要验证：

1. 处理完了所有评论
1. 任何提出意见的团队成员都已确认所提问题得到了解决
1. 通过了所有的自动化测试（永远不要合并测试失败的拉取请求）

在合并前一定要对提交者说谢谢，尤其是当他们就拉取请求中投入了大量精力时。

以下情况，团队成员可以立即合并拉取请求：

1. 小型文档修改
1. 杂事
1. 修复仓库上的其他工作（构建相关、测试相关、依赖性相关等）
1. 重要修复，需要纳入补丁发布

否则，团队成员在合并拉取请求前应遵守一个等待期：

* 如果拉取请求是在周一至周五发起的，则应等待 **2 天**。
* 如果拉取请求是在周六或周日发起的，则应等待 **3 天**。

这个等待期可以确保其他团队成员在合并前有机会审查该拉取请求。

如果拉取请求是基于 `eslint/eslint` 仓库分支（而非分叉），则在合并拉取请求后应该删除该分支（GitHub 会在合并拉取请求后会显示“删除分支（Delete branch）”按钮）。

**注意**：在没有收到其他团队成员反馈的情况下，你不应该合并自己的拉取请求。

## 何时关闭拉取请求

有几种情况下，可以关闭拉取请求而不进行合并：

1. 拉取请求解决的是已经被修复的问题
1. 该拉取请求 30 天内没有更新了
1. 拉取请求的提交者不愿遵守项目指南

在任何这些情况下，请务必留下评论，说明为什么要关闭该拉取请求。

### 关闭评论的例子

如果拉取请求 30 天没有更新了：

> 因为已经 30 天没有活动了所以我们将关闭它。如果你仍然对提交这段代码感兴趣，请随时重新提交。

如果拉取请求的提交者不愿意遵守项目指南：

> 不幸的是，我们不能接受不遵循我们准则的拉取请求。我现在要关闭这个拉取请求，但如果你愿意按照我们的指导方针重新提交，我们很乐意审查。
