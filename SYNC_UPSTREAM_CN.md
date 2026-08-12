# 从上游仓库拉取更新

本仓库是 [langchain-ai/open_deep_research](https://github.com/langchain-ai/open_deep_research) 的 fork。要保持你的 fork 与上游仓库同步，可以使用以下方法：

## 方法一：自动同步（推荐）

我们配置了 GitHub Actions 工作流，每周自动检查上游仓库的更新，如果有更新会自动创建 Pull Request。

**手动触发同步：**

1. 访问本仓库的 [Actions 标签页](../../actions/workflows/sync-upstream.yml)
2. 点击 "Sync with Upstream" 工作流
3. 点击 "Run workflow" 按钮
4. 选择分支后点击 "Run workflow"

工作流会：
- 从上游获取最新更改
- 如果有更新则创建 Pull Request
- 如果有合并冲突会通知你手动解决

## 方法二：命令行手动同步

如果你更喜欢手动同步或需要更多控制：

### 1. 添加上游远程仓库（一次性设置）

```bash
git remote add upstream https://github.com/langchain-ai/open_deep_research.git
git remote -v
```

### 2. 获取上游更改

```bash
git fetch upstream
```

### 3. 切换到默认分支

```bash
git checkout main  # 或你的默认分支
```

### 4. 合并上游更改

```bash
git merge upstream/main
```

如果有合并冲突：
1. 在编辑器中打开冲突文件
2. 查找冲突标记（`<<<<<<<`、`=======`、`>>>>>>>`）
3. 解决冲突，选择保留哪些更改
4. 暂存已解决的文件：`git add <文件>`
5. 完成合并：`git commit`

### 5. 推送更改到你的 fork

```bash
git push origin main
```

## 方法三：使用 GitHub 网页界面

1. 在 GitHub 上打开你的仓库
2. 你会看到类似 "This branch is X commits behind langchain-ai:main" 的消息
3. 点击 "Sync fork" 按钮
4. 点击 "Update branch" 同步上游

**注意：** 此方法仅在没有冲突时有效。对于复杂的合并，请使用方法一或方法二。

## 更多信息

查看 [CONTRIBUTING.md](CONTRIBUTING.md) 获取更详细的英文文档。
