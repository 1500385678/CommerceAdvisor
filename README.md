# CommerceAdvisor

> 25-商务-Commerce Leve 行业 Web 项目 · 商务 / 贸易 / 零售 / 电商 知识库

[![main](https://img.shields.io/badge/branch-main-blue)]()
[![phase](https://img.shields.io/badge/phase-0%20init-yellow)]()
[![license](https://img.shields.io/badge/license-internal-lightgrey)]()

---

## 一、项目定位

- **领域**:商务 / 贸易 / 零售 / 电商
- **形式**:静态/轻量 Web 站点,展示 _CommerceLib 10 大子库的内容
- **数据源**:`_CommerceLib/01_商务起源与演变` ~ `10_商务趣闻与奇观`
- **预期读者**:商务学习者、贸易从业者、跨行业研究者
- **核心风格**:工程化、结构化、可入库,避免 AI 味(参见 `25-商务-Commerce Leve/.Core/TOOLS.md`)

---

## 二、技术栈(P0.3 2026-08-27 落槌)

| 维度 | 选型 | 状态 |
|------|------|------|
| 渲染方式 | **纯静态 HTML/CSS/JS** | ✅ P0.3 落定(2026-08-27) |
| 构建配置 | **无构建** | ✅ P0.4 收尾(2026-08-29) |
| 内容格式 | Markdown(MD)→ 静态页 | 已落定 |
| 数据访问 | 文件直读(_CommerceLib 子库) | 已落定 |
| 部署 | Vercel / GitHub Pages | ✅ P0.7 落定(2026-09-17) · Vercel |

> **选型理由(2026-08-27 落槌)**:
> 1. **场景契合**:11 页内容站 + 几乎无交互逻辑,SSR/CSR 价值不大,纯静态渲染足够。
> 2. **零依赖体积**:免去 `package.json` / `node_modules`,仓库保持纯文本可入库。
> 3. **部署最简**:Vercel / GitHub Pages 一键托管,CDN 静态分发,构建成本 ≈ 0。
> 4. **可演进**:若 Phase 2 引入搜索/检索,再评估 Vite+TS 增量迁移,不锁死路径。
>
> **对 P0.4 的影响**:纯静态选型下 `package.json` 可选;`.gitignore` 已含 `dist/` / `node_modules/` 规则,无需新增;`python3 -m http.server` 即可本地预览。

---

## 三、目录约定

```
CommerceWeb/
├── README.md              # 本文件(项目门面)
├── .gitignore             # 忽略规则(P0.2 配套,起 2026-08-25)
├── 项目开发计划.md        # 主计划(T1 维护)
├── .plan/                 # T4 日报(YYYYMMDD.md,提交后由 T5 删除)
│   └── .DS_Store          # ← 已由 .gitignore 过滤
└── .Log/                  # 巡检报告(每日 02:00 cron 生成)
```

**写入规则**:
- `项目开发计划.md` — 仅 T1(主计划维护者)可改
- `.plan/YYYYMMDD.md` — 仅 T4(每日增量)写,提交后由 T5 删除
- `.Log/巡检-商务-YYYYMMDD.md` — T4 巡检自动生成
- `_CommerceLib/` 下原始资料库 — **只读引用,任何修改前需确认**

---

## 四、构建与预览

> 当前 Phase 0 阶段,尚无构建配置(P0.4 待办)。
> 临时本地预览:用任意静态服务器打开根目录即可。

```bash
# 方式 1:Python 内置
python3 -m http.server 8000

# 方式 2:Node 简易服务(P0.4 后改为正式构建)
npx serve .
```

打开 `http://localhost:8000` 浏览。

---

## 五、版本与发布

- **主仓库**:`1500385678/CommerceAdvisor`(GitHub)
- **镜像仓库**:`architectzy/CommerceAdvisor`(Gitee,推送主路径)
- **分支策略**:`main` 单分支直推
- **commit 规范**:参见 `项目开发计划.md` 维护规则
- **远程凭据**:由 `source /Users/aaron/Mac/Consultant/_ConsultantLib/.github-sync/env.sh` 注入
- **部署 URL**:`TBD`(P0.7 拍板 Vercel · 待 import 完成后回填;操作需张勇在 Vercel dashboard 一键 import `1500385678/CommerceAdvisor` 仓库,选 main 分支 + 默认 Vite-less 静态 build 跳过 build command → output 即仓库根目录)

---

## 六、相关链接

- 行业主目录:`../`(25-商务-Commerce Leve)
- 资料库:`../_CommerceLib/`
- 顾问 agent:`agent-6eeaa3be5068`(25-商务-Commerce Leve)
- 主计划:`./项目开发计划.md`
- 巡检记录:`./.Log/`

---

## 七、变更记录

| 日期 | 变更 | 来源 |
|------|------|------|
| 2026-08-24 | 项目起步,README 1 行占位 | T4 初始化 |
| 2026-08-25 | 充实 README 至七章:定位/技术栈/目录/构建/版本/链接/变更 | T4 cron 推进 P0.2 |
| 2026-08-26 | 新增 TEMPLATE-plan.md · 6 段必填模板 · .plan/ 命名规范 | T4 cron 推进 P0.5 |
| 2026-08-27 | 落槌 P0.3 技术栈:纯静态 HTML/CSS/JS,4 条选型理由入表 | T4 cron 推进 P0.3 |
| 2026-08-28 | 落盘 P1.1 `index.html`(Phase 1 破零) | T4 cron 推进 P1.1 |
| 2026-08-29 | P0.4 收尾:checkbox [x] + 纯静态「无构建」定调(README 二章加构建配置行) | T1 cron 收尾 |
| 2026-09-01 | 落盘 P0.6 `lib-index.md`(10 子库总览 + 引用边界 + Phase 1 映射) | T4 cron 推进 P0.6 |
| 2026-09-02 | 落盘 P1.2 `01-origin.html`(空壳 iframe 版,引用 _CommerceLib/01) | T4 cron 推进 P1.2 |
| 2026-09-03 | 落盘 P1.3 `02-branches.html`(沿用 01 模板,引用 _CommerceLib/02) | T4 cron 推进 P1.3 |
| 2026-09-04 | 落盘 P1.4 `03-logic.html`(沿用 02 模板,引用 _CommerceLib/03) | T4 cron 推进 P1.4 |
| 2026-09-05 | 落盘 P1.5 `04-stories.html`(沿用 03 模板,引用 _CommerceLib/04) | T4 cron 推进 P1.5 |
| 2026-09-06 | 落盘 P1.6 `05-games.html`(空壳 + 囚徒困境演示,引用 _CommerceLib/05) | T4 cron 推进 P1.6 |
| 2026-09-07 | 落盘 P1.7 `06-masters.html`(空壳 + 5 章速览,引用 _CommerceLib/06;9/7 落盘漏 commit,9/8 巡检代收尾) | T4 cron 推进 P1.7 |
| 2026-09-08 | 落盘 P1.8 `07-thinking.html`(沿用 06 模板,引用 _CommerceLib/07) | T4 cron 推进 P1.8 |
| 2026-09-09 | 落盘 P1.9 `08-modeling.html`(沿用 07 模板,引用 _CommerceLib/08) | T4 cron 推进 P1.9 |
| 2026-09-10 | 落盘 P1.10 `09-aesthetics.html`(沿用 08 模板,引用 _CommerceLib/09) | T4 cron 推进 P1.10 |
| 2026-09-11 | 落盘 P1.11 `10-curiosities.html`(沿用 09 模板,引用 _CommerceLib/10) · Phase 1 100% 收官(11/11) | T4 cron 推进 P1.11 |
| 2026-09-12 | `.gitignore:31` BUG 修复(删 `*.log` 通配规则,确保 `.Log/` 巡检报告可正常 `git add` 入仓无需 `add -f` 绕路) | T1 cron 暗修,9/16 T4 回溯补登变更行 |
| 2026-09-16 | 补 `.plan/20260916.md` 打破 9/12 ~ 9/16 连续 5 日 `.plan/` 静默断点 | T4 cron 推进 P0 巡检积压 |
| 2026-09-17 | 拍板 P0.7 部署平台 = Vercel,终结 8/27 起 21 日悬置;README 二章「部署」行「P0.7 待选」→「✅ P0.7 落定(2026-09-17) · Vercel」;五章加 1 行部署 URL 占位(待 Vercel import 后回填);`项目开发计划.md` P0.7 `[ ]` → `[x]` + 新增 9/17 变更行;Phase 0 永久 6/7 → 7/7 ✅;Phase 2 启动唯一显式阻塞项解除 | T1 cron 拍板 |
| 2026-09-18 | 落盘 P2.2 移动端适配(`index.html` 加 `@media (max-width: 600px)` 块 · 5 个子规则 · 纯 CSS 0 JS);Phase 2 启动空窗期 1 日终结;整体进度 18/23 = 78.3% → 19/23 = 82.6% | T4 cron 推进 P2.2 |
| 2026-09-19 | 落盘 P2.3 暗色模式(10 子页同步扩展 `@media (prefers-color-scheme: dark)` 块 · 复用 index.html 9/15 已实现 CSS 变量底子 · 覆盖 .frame-wrap / .toc .ch / .widget 3 个硬编码背景 · 纯 CSS 0 JS);`index.html` 注释同步;`项目开发计划.md` P2.3 `[ ]` → `[x]`;整体进度 19/23 = 82.6% → **20/23 = 87.0%**;`.plan/` 池 9/16 + 9/17 + 9/18 + 9/19(周六)连续 4 日起草,节奏稳态连续正式确认 | T4 cron 推进 P2.3 |
