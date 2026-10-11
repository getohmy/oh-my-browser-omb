# 版本记录 · Release notes

## 0.6.10 — 2026-10-11 · 已准备，待部署 / Prepared, deployment pending

- 修正 CLI doctor 的版本比较：已安装版本比升级提醒版本更新时，不再误报为过期。
- 本次不新增浏览器能力，不要求强制升级；安装版本与升级提醒仍分别控制。
- 部署完成后，通过官网安装器更新 CLI。此记录不表示服务器或 Lite 商店已经发布 0.6.10。

The patch corrects doctor version comparison when the installed CLI is newer than the announcement. Browser functionality is unchanged. No forced upgrade is required. This entry records preparation, not production or Lite store availability.

## 0.6.9 — 2026-10-10 · 服务端已部署 / Server deployment verified

- 导航与搜索遵守请求时间预算，保留超时、取消与结果未知的明确语义。
- 改善浏览器任务和标签页清理；搜索区分已确认无结果、页面错误与未知状态。
- 避免不明确的认证响应导致浏览器操作自动重放。
- 原生下拉框提供明确的 select 操作；异步内容可用 page watch 按就绪条件观察。
- 实机确认 API、CLI、Full 扩展为 0.6.9，异步观察、select、超时恢复和清理已验证。Lite 商店发布需单独审核；不要将服务端上线等同于商店版本已更新。

The deployed release improves bounded navigation/search, task and tab cleanup, search-result certainty and safe authentication recovery. Live checks verified API, CLI and Full 0.6.9 with async observation, semantic selection, timeout recovery and cleanup. Lite store publication remains a separate step.

安装 / Install: [官网指南](https://omb.org.cn/install) · [English guide](https://omb.org.cn/en/install)
