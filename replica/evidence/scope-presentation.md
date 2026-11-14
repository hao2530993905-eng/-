来源：助手本轮范围确认展示

## Zotero 10.0.6 探索结果与建议复刻范围

### 已实际走通
- **创建与整理**：新建分类、手动创建期刊并编辑标题/作者/出版物/日期、独立笔记、标签显示与筛选。
- **导入**：RIS 默认新建分类，标题、两位作者、期刊、卷期页码、DOI、摘要和关键词均正确。
- **附件与阅读**：PDF 子附件复制、自动重命名和索引；完整阅读器内查找文本，以 Control+Option+1 创建高亮并添加评论。
- **搜索与输出**：快速搜索、标题条件高级搜索、清空恢复；RIS/UTF-8 导出两条正确期刊记录。
- **维护与持久化**：设置分类、重复条目/空回收站只读视图；正常退出后的 SQLite 快照健康，重开后条目、笔记、PDF 高亮和评论保持。

### 建议纳入首版实现（等待你确认）
1. **创建、导入并整理文库**：item-entry、collections-tags、notes、import。
2. **附件阅读与注释**：attachments、reader-annotate。
3. **检索、引用与导出**：search、export-citation、styles。
4. **文库维护与偏好**：duplicates-trash、preferences-layout。
5. **同步与协作（保留但受阻）**：sync-groups；需专用测试账号和明确联网授权，当前未登录、未同步。

### 建议首版省略及影响
- **浏览器与 Word/LibreOffice 集成**：不保存网页或与文字处理软件通讯；本地导入、阅读和导出不受影响。
- **插件与开发者工具**：不兼容第三方插件，不提供调试入口。
- **AppleScript、zotero:// 与 RTF 扫描**：不提供系统自动化；GUI 可独立使用。
- **在线订阅 feeds**：不支持 RSS/OPML 在线更新；本地文献导入不受影响。

### 限制与未决事项
- 运行中主库使用 SQLite EXCLUSIVE 锁，逐动作在线数据库差分仍受阻；退出状态快照已通过完整性及外键检查。
- 截图均已保存，但当前模型不能直接读取图像，像素级视觉复核需支持图像的 Agent 或人工完成。
- 四个历史状态缺少逐状态恢复路径；已从后继状态重建全新空文库并验证恢复。
- 标签添加已看到结果，但两条正式动作轨迹被动态编辑器中断；取消、错误、边界、永久删除、复杂注释及外部服务仍需分批补查。
- REA 因本机 Node 补丁版本不满足要求未运行；已使用本地包/JavaScript/AX 证据，未做原生反编译。

探索摘要：`/Users/computeruse/Desktop/zotero复刻/replica/exploration/functions.md`。
状态与动作：`/Users/computeruse/Desktop/zotero复刻/replica/exploration/ui-states.md`。
机器状态：`/Users/computeruse/Desktop/zotero复刻/replica/features.json`、`exploration.json`、`evidence.json`。

**请回复“确认范围”以按上述清单进入后续实现，或指出要增加/省略/继续补查的项目。当前仅完成探索，尚未构建复刻版。**
