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
| 内容格式 | Markdown(MD)→ 静态页 | 已落定 |
| 数据访问 | 文件直读(_CommerceLib 子库) | 已落定 |
| 部署 | Vercel / GitHub Pages | P0.7 待选 |

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
