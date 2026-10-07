# Public · 静态资源

站点静态资源放这里（图片、字体、favicon、JSON 数据）。

- `*.json` 可被页面 `public from:[xxx]` 引用，其中的键通过 `@key` 占位符注入模板（如 `@title`）。
- 其余文件构建时原样复制到 `dist/assets/`。
