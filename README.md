# ☁️ 云投票器

一个基于 GitHub Pages 的在线投票应用，支持数据云存储。

## 功能特性

✅ **创建投票** - 自定义标题、描述和选项  
✅ **在线投票** - 实时投票和结果统计  
✅ **数据持久化** - 本地 LocalStorage 存储  
✅ **云同步** - 通过 GitHub API 同步到仓库  
✅ **实时统计** - 可视化投票结果展示  
✅ **完全免费** - 基于 GitHub Pages 和 API  

## 使用方法

### 1️⃣ 启用 GitHub Pages

1. 进入仓库 **Settings**
2. 找到 **Pages** 部分
3. 选择 **Deploy from a branch**
4. 选择 **main** 分支，**/ (root)** 目录
5. 点击 Save

几分钟后，你的投票器将发布在：
```
https://leocker-proplus.github.io/-/
```

### 2️⃣ 创建投票

1. 在页面中输入投票标题
2. 添加投票选项（至少 2 个）
3. 点击"创建投票"

### 3️⃣ 进行投票

- 点击任意选项按钮进行投票
- 实时查看投票结果和百分比

### 4️⃣ 云同步数据（可选）

**获取 GitHub Token：**

1. 访问 https://github.com/settings/tokens
2. 点击 "Generate new token (classic)"
3. 输入令牌名称（如 "Voter Token"）
4. 勾选权限：`public_repo`
5. 生成 Token 并复制

**同步数据：**

1. 在应用设置区粘贴 Token
2. 点击"💾 同步到 GitHub"
3. 数据将保存到 `votes.json`

**下次加载数据：**

1. 粘贴同一个 Token
2. 点击"📥 从 GitHub 加载"

## 数据存储方式

- **本地存储**：数据保存在浏览器 LocalStorage 中
- **云存储**（可选）：通过 GitHub API 同步到 `votes.json` 文件

## API 说明

### GitHub API 调用流程

```
GET /repos/{owner}/{repo}/contents/{file}
↓
获取文件内容和 SHA

PUT /repos/{owner}/{repo}/contents/{file}
↓
更新文件内容
```

**费用**：完全免费（GitHub API 免费配额足够）

## 技术栈

- **前端**：HTML5 + CSS3 + Vanilla JavaScript
- **存储**：Browser LocalStorage + GitHub API
- **托管**：GitHub Pages
- **数据格式**：JSON

## 文件结构

```
leocker-proplus/-/
├── index.html          # 主应用（所有功能集成）
├── votes.json          # 投票数据存储
└── README.md           # 使用说明（此文件）
```

## 浏览器兼容性

✅ Chrome 90+  
✅ Firefox 88+  
✅ Safari 14+  
✅ Edge 90+  

## 注意事项

1. **Token 安全**：不要将 Token 分享给他人
2. **公开仓库**：投票数据存储在公开仓库中
3. **浏览器存储**：LocalStorage 基于每个浏览器和域名

## 常见问题

**Q：如何删除投票？**  
A：点击投票下方的"🗑️ 删除投票"按钮

**Q：数据会丢失吗？**  
A：不会。数据保存在 LocalStorage 中，即使关闭浏览器也不会丢失。使用 GitHub 同步可以实现多设备同步。

**Q：支持多少个投票？**  
A：无限制，受浏览器 LocalStorage 大小限制（通常 5-10MB）

**Q：能否限制投票次数？**  
A：当前版本暂不支持，可以手动删除重新创建

## 反馈与改进

有问题或建议？欢迎提交 Issue！

---

**Made with ❤️ on GitHub Pages**
