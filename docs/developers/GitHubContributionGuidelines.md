# GitHub 项目合作指南

在 GitHub 上进行项目合作时，了解一些基本的 Git 操作是至关重要的。以下是一个简洁的指南，帮助高效地进行团队协作。

## 1. 克隆仓库到本地

### 步骤：

1. 打开项目的 GitHub 页面。
2. 点击 **Clone** 按钮，复制仓库的 URL。
3. 在终端中使用以下命令克隆仓库：
    ```bash
    git clone https://github.com/owner/repository.git
    ```
   替换 `owner` 和 `repository` 为仓库的拥有者和名称。

4. 进入本地仓库目录：
    ```bash
    cd repository
    ```

## 2. 设置远程仓库

在本地仓库中进行更改前，确保你的本地仓库和原仓库保持同步。

### 步骤：

1. 设置远程仓库（如果没有设置）：
    ```bash
    git remote add upstream https://github.com/original-owner/repository.git
    ```
   替换 `original-owner` 和 `repository` 为原仓库的所有者和名称。

2. 验证远程仓库：
    ```bash
    git remote -v
    ```

## 3. 创建并切换到新分支

每次开发前，都应创建新的分支进行功能开发，避免直接在 `main` 分支上进行开发。

### 步骤：

1. 在本地仓库上创建并切换到新的分支：
    ```bash
    git checkout -b new-feature
    ```
    `new-feature` 是你要创建的分支名称，可以根据你要开发的功能来命名。

2. 使用 `git branch` 检查当前分支：
    ```bash
    git branch
    ```
    输出将会显示你当前在哪个分支。

## 4. 开发并提交更改

在你开发完成后，进行提交（commit）以保存你的更改。

### 步骤：

1. 查看文件状态：
    ```bash
    git status
    ```

2. 添加修改的文件：
    ```bash
    git add .
    ```
    `.` 表示将所有更改过的文件添加到暂存区。如果你只想添加特定文件，可以替换 `.` 为文件名。

3. 提交更改：
    ```bash
    git commit -m "Add new feature"
    ```
    将 `"Add new feature"` 替换为一个简洁且有意义的提交信息。

## 5. 在提交前更新主分支代码

为了避免冲突，建议每次开发前先拉取主分支的最新代码。

### 步骤：

1. 切换到主分支：
    ```bash
    git checkout main
    ```

2. 拉取远程主分支的最新代码：
    ```bash
    git pull upstream main
    ```

3. 切换回你之前创建的功能分支：
    ```bash
    git checkout new-feature
    ```

4. 将主分支的更改合并到当前分支：
    ```bash
    git merge main
    ```
    如果有冲突，Git 会提示你解决冲突。解决完后，记得再次提交。

## 6. 推送更改到远程仓库

当你完成开发并希望将更改上传到 GitHub 时，需要将本地分支推送到远程仓库。

### 步骤：

1. 推送本地分支：
    ```bash
    git push origin new-feature
    ```

## 7. 提交 Pull Request (PR)

1. 在 GitHub 上打开你的仓库页面，点击 **Compare & pull request** 按钮。
2. 填写 PR 标题和描述，然后点击 **Create pull request**。
3. 确保 PR 中的更改与你的分支一致，且没有冲突。

## 8. 代码审查和合并

在你提交 PR 后，团队成员会对你的代码进行审查。根据审查结果，你可能需要进行修改并再次提交更改。审查通过后，PR 会被合并到主分支。

## 9. 注意事项

- **保持主分支更新**：每次开始开发前，确保你的主分支是最新的，避免合并冲突。
- **避免直接在主分支上开发**：总是创建一个新的功能分支来进行开发。
- **提交信息清晰简洁**：提交时，务必写清楚你做了什么更改，让别人容易理解。
- **解决冲突**：当合并时遇到冲突，使用 `git status` 查看冲突文件，手动解决冲突后，记得提交解决冲突后的文件。

---

通过遵循这些基本的 Git 操作，将能够高效协作，顺利进行项目开发。

