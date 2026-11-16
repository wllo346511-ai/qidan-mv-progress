# qidan-mv-progress

奇蛋物语 MV 的进度记录仓库（私有）。主文件：[进度.md](进度.md)。

## 入库规则

- 只提交文档和小型文本（md / json / txt 等）；小于 5MB 的图片也可以入库。
- 视频、模型权重一律不入库（`.gitignore` 已按扩展名排除）。
- 大于 5MB（5242880 字节）的文件禁止提交：`.gitignore` 无法按大小过滤，由 `hooks/pre-commit` 在 commit 时检查暂存区并拦截。

## 新克隆后启用大小拦截（一次性）

```powershell
git config core.hooksPath hooks
```

## 日常更新

每跑完一次生成，按 [进度.md](进度.md) 底部"每跑完一次怎么更新本文"操作，然后：

```powershell
git add -A ; git commit -m "镜头XX：第N跑 结果摘要" ; git push
```

媒体文件（mp4、模型等）留在仓库外的原位置（E:\奇蛋物语\ 等），进度.md 里用相对路径引用。
