# gitthub的进阶学习笔记

## 一.多人开发写作流程

- A在自己的计算机仓库中建立本地仓库
- A在github中创立远程仓库
- A将本地仓库推送到远程仓库
- B克隆远程仓库到本地开发
- B将本地仓库中的开发内容上传到远程仓库
- A将远程仓库最新内容拉回到本地

## 二.对Git的使用（上传文件的总步骤）

### 步骤1：准备工作

1.下载安装Git

2.在Github上创建一个新仓库（**创建时不要选README.md或.gitignore**）

3.创建好以后复制仓库的HTTPS或者SSH地址 

---

### 步骤2：初始化本地仓库

1. **打开 Git Bash**，进入你的文件夹：
   ```bash
   cd /path/to/your/folder
   ```
   - 例如：`cd d:/my-project`

2. **初始化本地仓库**：
   ```bash
   git init
   ```
   - 这会创建一个隐藏的 `.git` 文件夹（表示仓库已初始化）。

---

### **步骤 3：将文件添加到本地仓库**
1. **添加所有文件到暂存区**：
   ```bash
   git add .
   ```
   - `.` 表示添加当前文件夹下的所有文件。

2. **提交文件到本地仓库**：
   ```bash
   git commit -m "第一次提交，初始化项目"
   ```
   - `-m` 后面的内容是提交的注释（必填）。

---

### **步骤 4：关联远程仓库（GitHub）**
1. **添加远程仓库地址**：
   ```bash
   git remote add origin 你的GitHub仓库地址
   ```
   - 例如：`git remote add origin https://github.com/你的用户名/仓库名.git`

2. **推送到远程仓库**：
   ```bash
   git push -u origin main
   ```
   - 如果是旧版 Git，分支名可能是 `master`，用 `git push -u origin master`。
   - 第一次推送需要输入 GitHub 账号密码（或 Personal Access Token）。

---

### **关键命令总结**
```bash
cd /你的文件夹路径      # 进入文件夹
git init               # 初始化本地仓库
git add .              # 添加所有文件到暂存区
git commit -m "注释"   # 提交到本地仓库
git remote add origin 你的仓库地址  # 关联远程仓库
git push -u origin main          # 推送到远程仓库
```

---

### **注意事项**
1. 如果首次使用 Git，需先配置用户名和邮箱：
   ```bash
   git config --global user.name "你的名字"
   git config --global user.email "你的邮箱"
   ```

2. 如果推送失败：
   - 检查远程地址是否正确（`git remote -v`）。
   - 确保 GitHub 仓库已创建且分支名称匹配（`main` 或 `master`）。

---

## 三.Fork和Pull request的使用

### **1. Fork 是什么？**
- **Fork** 是将别人的仓库复制到你自己的 GitHub 账户下。
- 你可以在自己的 Fork 中自由修改代码，而不会影响原仓库。
- 通常用于为开源项目贡献代码。

#### **如何使用 Fork**
1. 找到你想贡献的项目仓库（例如：`https://github.com/owner/repo`）。
2. 点击右上角的 **Fork** 按钮。
   - 这会在你的 GitHub 账户下创建一个相同的仓库（例如：`https://github.com/your-username/repo`）。

---

### **2. Pull Request 是什么？**
- **Pull Request（PR）** 是将你的修改提交给原仓库的请求。
- 原仓库的维护者可以审查你的代码，决定是否合并到主仓库。

#### **如何创建 Pull Request**
1. **克隆你的 Fork 到本地**：
   ```bash
   git clone https://github.com/your-username/repo.git
   ```

2. **创建新分支并修改代码**：
   - 创建一个新分支（例如：`feature-branch`）：
     ```bash
     git checkout -b feature-branch
     ```
   - 修改代码后，提交更改：
     ```bash
     git add .
     git commit -m "添加了新功能"
     ```

3. **推送分支到你的 Fork**：
   ```bash
   git push origin feature-branch
   ```

4. **在 GitHub 上创建 Pull Request**：
   - 进入你的 Fork 仓库页面。
   - 点击 **Pull Request** 按钮。
   - 选择你的分支（例如：`feature-branch`），并填写 PR 的标题和描述。
   - 点击 **Create Pull Request**。

---

### **3. 如何与他人协同工作**
1. **同步原仓库的更新**：
   - 添加原仓库为远程仓库：
     ```bash
     git remote add upstream https://github.com/owner/repo.git
     ```
   - 拉取原仓库的最新代码：
     ```bash
     git fetch upstream
     git merge upstream/main
     ```

2. **解决冲突**：
   - 如果原仓库的代码和你的修改有冲突，Git 会提示你解决冲突。
   - 编辑冲突文件，解决冲突后提交：
     ```bash
     git add .
     git commit -m "解决冲突"
     ```

3. **审查和合并 Pull Request**：
   - 如果你是项目维护者，可以审查他人的 PR，决定是否合并。
   - 在 PR 页面点击 **Merge Pull Request** 即可合并代码。

---

### **4. 协作流程总结**
1. **Fork 仓库**：复制别人的仓库到自己的账户。
2. **克隆到本地**：将 Fork 的仓库克隆到本地。
3. **创建分支**：为新功能或修复创建分支。
4. **修改代码**：在分支上完成修改并提交。
5. **推送分支**：将分支推送到你的 Fork。
6. **创建 PR**：向原仓库提交 Pull Request。
7. **审查和合并**：维护者审查并合并 PR。

---

### **5. 注意事项**
- **保持分支干净**：每个功能或修复使用单独的分支。
- **写清晰的提交信息**：方便他人理解你的修改。
- **及时同步原仓库**：避免代码冲突。







