# 日常开销管理 · Budget Tracker H5

按月或按周设置预算 + 消费记录，纯前端，数据保存在浏览器本地（SQLite via sql.js + localStorage）。

## 在线使用（主入口）

**请只用这一个地址：**

https://997wxr-hub.github.io/expense-manager/

| 说明 | |
|------|--|
| 旧 Vercel 链接 | `expensemanager-h5.vercel.app` — 已弃用为主入口，数据与 GitHub Pages **不互通** |
| 国内镜像 | 可用自有域名 `outputloggo.com`（腾讯云 COS）另行部署，见下方 |

手机：浏览器打开 → 可「添加到主屏幕」（PWA）。

> 换网址 / 换浏览器 = 本地数据不会自动跟过去。换入口前请先 **导出 CSV**。

## 功能

- **记账周期**：设置里可切换「按月 / 按周」（默认按月）
- 本期预算 / 进度条 / 超支提醒（自动沿用上一期预算）
- **自定义一级 / 二级分类**（改名同步历史记录）
- 多币种（AUD / CNY / USD）+ 汇率（联网自动 / 离线手动）
- 分类饼图、本期 vs 上期对比、月度总览
- CSV 导出、搜索、离线 Service Worker

## 本地运行

```powershell
cd C:\Users\WuXinrui\Projects\expense-manager
# 需 HTTP 服务（sql.js WASM）
..\scripts\Serve-Project.cmd expense-manager
```

浏览器打开 http://127.0.0.1:3456/

## 项目结构

```
expense-manager/
├── index.html
├── manifest.json / sw.js / icon-*.png
├── vendor/          # sql.js + Chart.js（已本地化）
└── .github/workflows/pages.yml
```

## 隐私

- 无账号、无后端、无上传
- 数据仅存本机浏览器

## 国内访问（outputloggo.com）

域名已指向腾讯云上海 COS（DNSPod），适合做国内静态托管镜像。

注意：

1. COS 上的站点和 GitHub Pages **是两个不同 origin**，本地记账数据不会自动同步。
2. 建议用子域名，例如 `expense.outputloggo.com`，避免覆盖现有 `work-traker` 桶内容。
3. 需在腾讯云 COS 开启静态网站、绑定自定义域名并配置 HTTPS 证书。
4. 上传本仓库静态文件（`index.html`、`vendor/`、`sw.js`、图标等）到桶根或子路径即可。

## 源码来源

自 `Desktop\好玩的小工具\weekly budget files H5\expense_manager.html` 迁入并加固。
