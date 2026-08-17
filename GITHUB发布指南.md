# GitHub 发布指南（新手版）

目标：把 `lgcm_template/` 公开成一个免费仓库，作为方法页与引流入口。
本机已装好 git，只需在网页建仓 + 几条命令即可。

## 0. 注册
- 打开 https://github.com ，用邮箱注册，记住你设的 **用户名（username）**。
- 首次提交/推送时，GitHub 会让你登录授权（按弹窗提示操作）。

## 1. 在 GitHub 网页上建仓库
- 右上角「+」→ **New repository**。
- Repository name：`mg-lgcm-template`
- 可见性选 **Public**（公开）。
- **不要**勾选 "Initialize this repository with a README"（我们本地已有文件）。
- 点 **Create repository**。
- 建好后页面会显示一个仓库地址，形如：
  `https://github.com/<你的用户名>/mg-lgcm-template.git`

## 2. 本地关联并推送
在 `lgcm_template/` 目录里，把 `<你的用户名>` 换成上面真实的用户名，依次执行：

```bash
git remote add origin https://github.com/<你的用户名>/mg-lgcm-template.git
git branch -M main
git commit -m "MG-LGCM reproducible template (synthetic data)"
git push -u origin main
```

> 提示：文件此前已 `git add -A` 暂存（8 个文件）。`lgcm_paid_bundle/` 已被
> `.gitignore` 排除，不会进公开仓库——付费内容只在爱发电发。

## 3. 开启 GitHub Pages（让 index.html 成为在线方法页）
- 仓库页 → **Settings** → **Pages**。
- Source 选 **main** 分支、目录 **/(root)**，点 Save。
- 等一两分钟，访问 `https://<你的用户名>.github.io/mg-lgcm-template/`
  就是公开方法页（也是你放去爱发电引流的链接）。

## 4. 串联两条线
- 把上面的 Pages / 仓库链接，填进爱发电商品页「免费部分」作引流。
- 等你有了**爱发电店铺链接**，把它发给我（或自己填进本地 `index.html`
  的 CTA 占位处），再 `git commit` + `git push` 一次即可。

## 发布前必查
- [ ] `LICENSE` 里的 `[你的名字]` 已改成你的真实署名。
- [ ] 全仓库无真实数据、无论文识别信息（已净身，可复查）。
- [ ] 已 `git push`，Pages 能正常打开。
