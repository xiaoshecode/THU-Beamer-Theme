# THU-Beamer-Theme 维护说明

清华主题 LaTeX Beamer 演示模板。

- 上游：https://github.com/tuna/THU-Beamer-Theme
- 在线文档：https://xiaoshecode.github.io/xiaoshecode/repos/THU-Beamer-Theme/
- 检查日期：2026-10-30

## 环境与使用

- 准备含 ctex 的 TeX Live/MiKTeX 或使用原 README 的 Overleaf 模板。

使用/检查入口（需先满足依赖条件）：

- `xelatex -interaction=nonstopmode -halt-on-error slide.tex`
- `bibtex slide`
- `xelatex -interaction=nonstopmode -halt-on-error slide.tex`
- `xelatex -interaction=nonstopmode -halt-on-error slide.tex`

BibTeX 后连续运行两次 XeLaTeX，第二次用于解析正文中的引用标签。也可使用 `latexmk -xelatex slide.tex` 自动完成所需轮次。

## 目录职责

- slide.tex — 示例入口
- Tsinghua.sty — 主题样式
- pic/ — 标志图片
- ref.bib — 参考文献

## 本次整理

- 新增维护文档和在线文档入口，补全用途、目录、使用路径及验证边界。
- 补齐 BibTeX 后第二次 XeLaTeX，避免首次构建仍显示未解析的引用。

## 检查记录

- **仓库目录与入口盘点**（passed）：检查 Git 索引中的 8 个路径、README 和项目配置；不等于功能验收。
- **完整构建与端到端运行**（not_run）：未完成模板编译和版面验证，具体字体依赖取决于本机 TeX 环境。
- **引用编译流程**（passed）：使用本仓库 ref.bib 和 origin 引用的最小文档，XeLaTeX → BibTeX → XeLaTeX 后仍有未定义引用，再运行一次 XeLaTeX 后消失。完整模板试编译在 EPS 图片转换阶段停止，该问题未归因于本次文档改动。

## 验证边界与待办

- 未完成模板编译和版面验证，具体字体依赖取决于本机 TeX 环境。

## 后续维护约定

保留上游许可证与作者信息。沿用现有模块边界和格式配置；修复功能时同步最小回归验证。依赖或接口变更需写明迁移步骤，避免仅为目录美观搬动公开入口。
