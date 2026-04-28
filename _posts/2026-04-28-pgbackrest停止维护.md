---
title: "pgBackRest 作者宣布停止维护该项目"
description: "PostgreSQL 知名备份恢复工具 pgBackRest 的维护者 David Steele 正式宣布项目存档停止维护，因被 Snowflake 收购后新东家无意资助。"
dateFormatted: "Apr 28, 2026"
tags: ["PostgreSQL", "pgBackRest", "开源", "数据库", "备份工具"]
---

**PostgreSQL 备份恢复项目 pgBackRest 的维护者 David Steele 宣布项目存档停止维护。**

Steele 解释说，过去 13 年 pgBackRest 是他倾注热情的项目，幸运的是大部分时间里他都有企业资助。他的长期赞助商是 **Crunchy Data** 公司，但这家公司被 **Snowflake** 收购了，而新东家无意资助他继续从事相关工作。

因此他过去几个月一直在寻找继续这项工作的职位，但没有成功，获得的赞助也远远未能达到维持项目运营所需的金额。所以他只能宣布停止维护。

pgBackRest 被广泛视为 PostgreSQL 生态系统最流行的运维工具之一，是功能最完整的 PostgreSQL 备份工具，支持：

- 块级增量备份
- 并行恢复
- 页面校验和验证
- S3/Azure/GCS 对象存储支持
- 加密备份

## 当前赞助商

目前仅剩 **Supabase** 仍在赞助，过去的赞助商包括 Crunchy Data 和 Resonate。

## 项目现状

Steele 在公告中写道：

> “归根结底，我也需要谋生。与其做得马马虎虎或断断续续，不如来个干脆的停止。”

他建议，如果有人想 fork 这个项目，请**选一个新名字**。

## 影响评估

pgBackRest 被普遍认为是 PostgreSQL 生态系统中**功能最完整**的备份工具，此次停止维护将对大量生产环境产生影响。

好消息是，项目代码仍然可用（MIT 许可证），社区有可能接手继续开发。

---

*来源：[pgBackRest GitHub 仓库](https://github.com/pgbackrest/pgbackrest#notice-of-obsolescence)*
