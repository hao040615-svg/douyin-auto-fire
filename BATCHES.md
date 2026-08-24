# 批量发送说明

本仓库支持将好友分成多个批次发送，避免抖音风控。

## 配置方式

### 方式一：使用预置的批量配置（推荐）

代码中已内置3个批量配置文件：
- `config/batches/batch1.json` - 第1批：江华、杨叶鹏、吴文耀、华雨欢、肥秋
- `config/batches/batch2.json` - 第2批：宸、杨思蓓、-C、吴卓昊、陈秋鑫
- `config/batches/batch3.json` - 第3批：老刘、徐少雄、陈佩奇

定时任务会在不同时间自动执行：
- 00:00 执行第1批
- 00:05 执行第2批
- 00:10 执行第3批

### 方式二：自定义配置

如果需要修改分组或添加新好友，请按以下步骤操作：

1. 编辑 `config/batches/batch1.json`、`batch2.json`、`batch3.json`
2. 在 GitHub Secrets 中添加对应的配置：
   - `DOUYIN_CONFIG_BATCH1` - 第1批的配置 JSON
   - `DOUYIN_CONFIG_BATCH2` - 第2批的配置 JSON
   - `DOUYIN_CONFIG_BATCH3` - 第3批的配置 JSON

## 手动触发

在 GitHub Actions 页面可以手动运行工作流，选择要运行的批次。
