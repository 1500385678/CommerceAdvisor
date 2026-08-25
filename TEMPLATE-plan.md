# TEMPLATE-plan.md · .plan/ 日报模板

> **用途**:T4 每日增量时,以此为模板复制为 `.plan/YYYYMMDD.md`,填入当日实际内容。
> **版本**:v1.0 · 起 2026-08-26 · P0.5 配套
> **维护**:T1(模板演进)/ T4(每日复制 + 填写)

---

## 一、命名规范(强约束)

| 项 | 规范 | 说明 |
|----|------|------|
| 文件名 | `.plan/YYYYMMDD.md` | 8 位日期,无分隔符 |
| 目录位置 | 仓库根 `.plan/` | 与 `.Log/` 平级,不嵌套 |
| 字符集 | UTF-8 / 中文 + 英文 | 兼容 Obsidian 渲染 |
| 单文件大小 | 建议 ≤ 8 KB | 过大请拆为「主 + 附」 |
| 命名空间 | 同一日期只允许 1 份 | 重做请覆盖,保留 commit 历史 |

## 二、生命周期

```
02:00  T4 巡检 agent 生成 .Log/巡检-商务-YYYYMMDD.md(同时也是当日开发项预告)
03:00  T4 执行 agent 复制本模板为 .plan/YYYYMMDD.md,填入当日实际内容
       └─ git add .plan/YYYYMMDD.md + commit "plan: CommerceAdvisor YYYYMMDD"
       └─ 同步 git push(gitee 主,github 镜像)
       └─ 归档删除:git rm .plan/YYYYMMDD.md + commit "docs: 商务 YYYYMMDD - 归档今日 plan"
```

> **关键纪律**:`.plan/YYYYMMDD.md` **不入主分支长期保留**,归档即删,完整内容保留在 git 历史中,避免 `.plan/` 体积膨胀。

## 三、模板正文(必填段)

> 以下 6 段是日报必填,缺一即视为未完成。

```markdown
# CommerceAdvisor · 日报 YYYYMMDD

> **日期**:YYYY-MM-DD(周X)
> **项目**:CommerceAdvisor(`_CommerceLib/CommerceWeb/`)
> **执行人**:T4 cron(行业 25-商务-Commerce Leve 顾问)
> **依据**:`.Log/巡检-商务-YYYYMMDD.md` 优先级 P0 项

---

## 一、今日挑选项

> 从 `项目开发计划.md` Phase 0/1/2 中选 1 个未完成 checkbox,记录选择理由。

- **checkbox**:`P?.? 简述`
- **选择理由**:…

## 二、实际产出

> 简洁可入库:1 段代码 / 1 段文档 / 1 个配置修改。

(此处填 1 段,≤ 50 行)

## 三、checkbox 更新

- [x] `P?.? 简述` ← YYYYMMDD 完成

## 四、commit 信息

- **commit hash**:(commit 后回填)
- **commit msg**:`plan: CommerceAdvisor YYYYMMDD`
- **gitee 状态**:成功 / 失败
- **github 状态**:成功 / 失败

## 五、风险与备注

(若无可省略)

## 六、明日交接

(留 1 段给 T4 明日或 T1 决策)
```

## 四、禁区(继承主计划)

- ❌ T4 不修改 `项目开发计划.md`(T1 专属)
- ❌ T4 不修改 README.md 主体(版本/链接/变更记录章除外,需 T1 同步)
- ❌ T4 不动 `_CommerceLib/` 下原始资料库(只读)
- ❌ T4 不在 .plan/ 留任何「占位 / TODO」字样,要么填完整,要么不提交

## 五、关联文档

- `项目开发计划.md` — 主计划(T1 维护)
- `README.md` — 项目门面(技术栈/目录约定章)
- `.Log/巡检-商务-YYYYMMDD.md` — 02:00 巡检报告
- `.Core/TOOLS.md`(行业根目录) — 风格规范,避免 AI 味

---

**变更记录**

| 日期 | 变更 | 来源 |
|------|------|------|
| 2026-08-26 | 初版,确立 .plan/ 命名规范 + 6 段必填模板 + 生命周期 + 禁区 | T4 cron 推进 P0.5 |
