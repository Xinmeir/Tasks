# Git版本回滚与冲突解决笔记

---

## 一、版本回滚

### 1. 查看提交历史
```bash
git log --oneline          # 精简版提交记录
git log --graph            # 带分支图的详细记录
git reflog                 # 查看所有操作记录（包括被删除的提交）
```

### 2. 回滚方式
#### (1) git reset（本地仓库回滚）
```bash
git reset --soft HEAD~1    # 回退到上一个提交，保留工作区改动
git reset --mixed HEAD~1   # 默认模式，回退提交且保留工作区改动，但取消暂存
git reset --hard HEAD~1    # 彻底回退到指定版本（慎用！！！会丢失未提交的修改）

# 回滚到具体commit
git reset --hard a1b2c3d   # 使用具体commit哈希值
```

#### (2) git revert（公共仓库推荐）
```bash
git revert HEAD           # 撤销最新提交，生成新提交记录
git revert a1b2c3d        # 撤销指定commit
git revert -m 1 <merge_commit> # 撤销合并提交
```

### 3. 回滚策略对比
| 方法   | 适用场景                      | 是否修改历史 | 是否保留提交记录 |
| ------ | ----------------------------- | ------------ | ---------------- |
| reset  | 本地分支/未推送的提交         | ✔️            | ❌                |
| revert | 已推送的提交/需要保留完整历史 | ❌            | ✔️                |

---

## 二、冲突解决全流程

### 1. 冲突产生场景
- git merge
- git rebase
- git pull
- git cherry-pick

### 2. 解决步骤
#### (1) 定位冲突文件
```bash
git status
# 显示 "Unmerged paths" 列表
```

#### (2) 手动解决冲突
打开冲突文件：
```diff
<<<<<<< HEAD
当前分支的内容
=======
要合并分支的内容
>>>>>>> branch-name
```

手动修改后保存文件，删除冲突标记

#### (3) 标记冲突已解决
```bash
git add <file>          # 添加解决后的文件
git commit -m "解决合并冲突"
```

### 3. 高级解决技巧
#### (1) 使用合并工具
```bash
git mergetool          # 调用配置的图形化工具（如meld、kdiff3）
```

#### (2) 中止合并
```bash
git merge --abort      # 放弃合并回到合并前状态
git rebase --abort     # 中止rebase操作
```

#### (3) 接受特定版本
```bash
git checkout --ours <file>    # 保留当前分支版本
git checkout --theirs <file>  # 采用合并分支版本
```

---

## 三、Rebase冲突处理

### 1. 交互式rebase流程
```bash
git rebase -i HEAD~3
```
出现冲突时：
1. 按上述步骤解决冲突
2. `git add` 标记解决
3. `git rebase --continue`
4. 若需跳过某次提交：`git rebase --skip`
5. 若完全放弃：`git rebase --abort`

---

## 四、预防冲突技巧

1. 频繁拉取更新
```bash
git pull --rebase
```

2. 合理分支策略
- 功能分支开发
- 定期合并主分支变更

3. 小颗粒度提交
- 每个提交只做单一功能修改

4. 使用.gitignore
- 排除自动生成文件

---

## 五、注意事项

1. **强制推送警告**
```bash
git push -f  # 仅限私有分支使用，公共分支慎用！
```

2. 重要修改前创建备份分支
```bash
git branch backup-branch
```

3. 使用stash暂存工作区
```bash
git stash        # 保存当前修改
git stash pop    # 恢复修改
```

---

## 六、经典问题解决方案

### 场景1：错误reset后恢复
```bash
git reflog                     # 找到丢失的commit哈希
git reset --hard <lost_commit>
```

### 场景2：错误合并后回退
```bash
git reset --hard ORIG_HEAD     # 快速回到合并前状态
```

---

## 总结表格

| 操作类型 | 常用命令           | 适用场景                   |
| -------- | ------------------ | -------------------------- |
| 本地回滚 | git reset --hard   | 彻底放弃未提交的修改       |
| 安全撤销 | git revert         | 需要保留提交历史的公共仓库 |
| 冲突解决 | 手动编辑 + git add | 合并/变基时的代码冲突      |
| 历史恢复 | git reflog + reset | 找回误删的提交             |

建议配合图形化工具（如SourceTree/VSCode插件）使用，可更直观查看提交历史和解决冲突。