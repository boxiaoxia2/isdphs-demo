# isdphs-demo

**ISDPHS 使用方仓库** —— 通过 npm 安装 [`isdphs`](https://www.npmjs.com/package/isdphs) 引擎，在一个独立仓库里用 `.isd` 声明式语言装配真实站点。

> 链路：**语言设计**（[《Isdphs 语言设计》](https://feishu.doubao.com/docx/NecodwIbto1OCRxw7jWc3McQnsg)，参照 Fluent UI + FAST）→ **模板/引擎仓库** [boxiaoxia2/isdphs](https://github.com/boxiaoxia2/isdphs)（引擎 + `create-isdphs` 脚手架，npm 分发）→ **本使用仓库**。

## 演示内容

| 能力 | 位置 | 说明 |
|---|---|---|
| npm 分发 | `package.json` → `isdphs` | 引擎以依赖方式引入，`npm run build` 即用 |
| 页面装配 | `Site/Page/index.page.isd` | Page = Layout 槽位 × Box 组件，`layout from` / `box from` / `public from` |
| 槽位契约 | `Site/Layout/main.layout.isd` | `header/main/footer` 三槽位 + `<{slot}>` 占位符 + 加载事件 |
| 自定义组件 | `Site/Box/*.box.isd` | Parts 部件 + 作用域 CSS + js 行为 + 语义令牌 |
| 组合定制 | `Site/Box/hero-card.box.isd` | 自定义组件内嵌套模块 Box `<zhuoyun-card>` |
| 模块分发 | `Modules/@zhouis/中舟韵/` | 组件以模块形式发布/安装，`isdphs.boxes` 声明入口 |
| 主题令牌 | `setting.json` + `theme-toggle` | Fluent 风格语义令牌，default/dark 一键切换 |

## 运行

```bash
npm install        # 安装 isdphs 引擎
npm run build      # isdphs build → dist/index.html + isdphs.css + isdphs.js
npm run dev        # isdphs dev → http://localhost:4173（监听 Site/ 自动重建）
```

## 本地验证（npm 发布前）

npm 包未发布时，可先用本地 tarball 验证：

```bash
npm install --no-save /tmp/isdphs-0.1.0.tgz   # 或 npm i file:../isdphs/packages/isdphs
npm run build
```

## 结构

```text
isdphs-demo/
├── setting.json          # 主题令牌（default/dark，含自定义 color.accent）
├── package.json          # 依赖 isdphs
├── Modules/              # 模块（组件分发单元）
│   └── @zhouis/中舟韵/    # 示例模块：zhuoyun-card
├── Local/                # 本地配置（不入库）
├── Site/
│   ├── Layout/           # main.layout.isd
│   ├── Page/             # index.page.isd
│   ├── Box/              # brand-header / hero-card / hello-button / theme-toggle / footer-box
│   └── Public/           # nav.json 等静态数据
└── .gitignore
```
