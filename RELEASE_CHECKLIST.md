# Release Checklist — 公开发布前逐项核对

> 适用场景：把 `lgcm_template/` 对外发布（GitHub / 个人主页 /
> 学术社区 / 咨询入口）。主要闸门是**"是否泄露保密数据或超出公开信息"**。

## 发布前必查（硬性）
- [ ] **无任何真实数据**：确认仓库/压缩包内只有 `lgcm_template.R`、`README.md`、
      `RELEASE_CHECKLIST.md` 及可选说明图；`simulate_data()` 为唯一数据来源，
      未嵌入任何真实记录或能反推真实队列的统计量。
- [ ] **代码可跑通**：在干净的 R 环境（仅装 `lavaan/semTools/dplyr/ggplot2`）
      执行 `source("lgcm_template.R")` 无报错，输出包含拟合指标与比较结果。
- [ ] **输出合理**：合成数据的组间模式方向应合理
      （Normal 截距最高、Obese 斜率最快；FVC 呈"fat-but-fit"）。
- [ ] **无冒用**：不冒用"真实结果"字样描述合成输出；所有输出均标注为合成演示。

## 方法严谨性（体现差异化卖点）
- [ ] **测量不变性**：第 4 节 scalar 拟合可接受（CFI/TLI 达标），且在文档中说明
      "scalar 是潜均值比较的前提"。
- [ ] **线性假设**：第 6 节已做线性 vs 二次对比；若二次显著，对外说明时措辞相应调整。
- [ ] **Satorra–Bentler**：所有嵌套比较均用 MLR 下的缩放 LRT（脚本已默认），
      不混用普通卡方差。

## 对外呈现（可信度）
- [ ] **许可证**：根目录含 `LICENSE`（MIT 或 CC-BY 4.0），`README` 注明方法来源。
- [ ] **免责声明醒目**：`README` 顶部"数据声明"保留，避免被误认为含真实数据。
- [ ] **清除草稿痕迹**：本模板无草稿批注；若你在其基础上扩展，确保不含 `这里是指…`
      `没有分号` 之类边注或 `obesity disadvantag` / `boyd mass index` 等笔误。

## 发布节奏建议
- [ ] 本模板仅含合成数据，**可随时公开发布**（无保密/预审风险）。
- [ ] 网络分析（GGM/EBICglasso）模板：**待相关方法可公开后再发布**，避免方法优先权风险。
- [ ] 发布后：以"可复现方法演示"定位，而非"售卖代码"。

## 发布操作（GitHub，免费引流入口）
本目录即仓库根。付费增值包在 `../lgcm_paid_bundle/`，已被 `.gitignore` 排除，不会进免费仓库。
1. 本地初始化（在本目录执行）：
   ```bash
   git init
   git add -A
   git commit -m "MG-LGCM reproducible template (synthetic data)"
   ```
2. 在 GitHub 新建公开仓库（如 `mg-lgcm-template`），关联并推送：
   ```bash
   git remote add origin <你的仓库URL>
   git branch -M main
   git push -u origin main
   ```
3. 仓库首页即 `README.md`；若想用 `index.html` 作项目主页，可在仓库
   Settings → Pages 选择 `main` 分支根目录（或 `docs/`），把 `index.html` 放进去。
4. 在 `README.md` 顶部或仓库描述里挂上爱发电/增值包链接，形成"免费看代码 → 付费买适配经验"的转化路径。
5. 推送前再核对：`.Rhistory` / `Rplots.pdf` 已被 `.gitignore` 排除；`../lgcm_paid_bundle/` 不应出现在 `git status` 中。

## 一句话闸门
**只要不出现真实数据、且所有输出都标注为合成演示，即可发布。**
