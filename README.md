# 日常开销管理 · Weekly Budget H5

周预算追踪 + 消费记录，纯前端，数据保存在浏览器本地（SQLite via sql.js + localStorage）。

## 在线使用

| 平台 | 链接 | 国内访问 |
|------|------|----------|
| **GitHub Pages** | https://997wxr-hub.github.io/expense-manager/ | 可能较慢，建议备用 |
| **Vercel（已有）** | https://expensemanager-h5.vercel.app | 海外快；国内不稳定 |

手机：浏览器打开 → 可「添加到主屏幕」（PWA）。

## 功能

- 周预算 / 进度条 / 超支提醒
- 多币种（AUD / CNY / USD）+ 汇率（联网自动 / 离线手动）
- 分类饼图、本周 vs 上周对比、月度总览
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
├── vendor/          # sql.js + Chart.js（已本地化，减少 CDN 依赖）
└── .github/workflows/pages.yml
```

## 隐私

- 无账号、无后端、无上传
- 数据仅存本机浏览器

## 给中国用户的说明

海外托管（GitHub Pages / Vercel）在国内**不保证**稳定访问。若需长期给国内用户用，建议后续：
- 备案 + 国内静态托管（阿里云 OSS / 腾讯云 / Gitee Pages）
- 或购买国内 CDN 回源

汇率 API（open.er-api.com）在国内可能失败；应用会自动用手动/缓存汇率。

## 源码来源

自 `Desktop\好玩的小工具\weekly budget files H5\expense_manager.html` 迁入并加固。
