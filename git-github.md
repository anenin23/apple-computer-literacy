在使用 github 时，需要先[配置 token](https://github.com/orgs/community/discussions/80843)



### Git 的使用

Git与GitHub的协作流程可分为日常开发的基础操作和团队协作进阶操作，以下是配置正确后的标准工作流指南：

1. 初始化项目（仅首次需要）
```bash
git init  # 本地创建新仓库
git remote add origin <仓库URL>  # 绑定GitHub远程仓库
```

2.常用的命令

```bash
git pull origin main  # 开始工作前同步最新代码[1]
# 进行代码修改...
git add .  # 添加当前目录所有变更（包含删除操作）[2]
git commit -m "描述变更内容的标题"  # 提交到本地仓库
git push -u origin main  # 推送到GitHub主分支[3]
```

3. 其他命令

- 处理文件删除

```bash
git rm 文件名  # 显式标记文件删除（替代直接删除文件）
git commit -m "移除废弃文件"
```

- 检查变更状态

```bash
git status  # 查看暂存区状态（红色未暂存/绿色已暂存）
git diff  # 查看具体代码修改内容
```

### GitHub
1. 分支管理
```bash
git checkout -b feature/new-module  # 创建功能分支
git push origin feature/new-module  # 推送分支到远程
# 在GitHub发起Pull Request进行代码审查
```

2. 版本回退
```bash
git log --oneline  # 查看提交历史
git reset --soft HEAD~1  # 撤销最近提交但保留修改
git reset --hard <commit-hash>  # 强制回退到指定版本
```

### 推荐工作习惯
- 每次提交前运行`git pull`避免代码冲突
- 保持提交信息原子化（每个提交只解决一个任务）
- 敏感数据使用`.gitignore`过滤（避免提交API密钥等）

