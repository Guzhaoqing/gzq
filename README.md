# 周转天数计算器

这是一个无服务器静态网页计算器，适合部署到 GitHub Pages、Vercel、Netlify 或 Cloudflare Pages。

## 计算规则

- `S = N / M * 24`
- 需卖/降库数量：`ROUNDUP((24N - 目标周转 * S) / (目标周转 + 24), 0)`
- 实际计入销量：`MAX(今日已签收, 需卖/降库数量)`，且不超过库存
- 可上单：先按箱托关系向下取整，再不超过整车数量上限
- 周转天数：有小数向上取整

## 发布

把本文件夹上传到 GitHub 仓库，然后在仓库 Settings > Pages 中选择 `Deploy from a branch`，分支选 `main`，目录选 `/root`。
