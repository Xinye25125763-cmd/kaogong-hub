# 考公资料总目录 · kaogong-hub

把散落的考公资料收进一个目录里。每个「文件夹」是一个 Git 子模块，指向独立的仓库，
所以既能像翻目录一样浏览，又能各自跟进上游更新。

## 分区

| 分区 | 内容 | 来源仓库 | 体量 |
|:--|:--|:--|--:|
| [`01-备考技能`](https://github.com/KeWang0622/kaogong-skill) | 公务员与事业单位 AI 备考技能：行测、申论、职测、综应、公基、公文、面试与错题复盘。支持 Agent Skills 与单文件使用 | `KeWang0622/kaogong-skill` | 3.5 MB |
| [`02-行测真题`](https://github.com/ERRRC/xingcezhenti) | 2016–2026 年国考 + 省考行测全部真题 | `ERRRC/xingcezhenti` | 340 MB |
| [`03-上岸教程`](https://github.com/miss-mumu/developer2gwy) | 公务员从入门到上岸，面向程序员的考公实践教程 | `miss-mumu/developer2gwy` | 1.4 MB |

## 怎么用

```bash
# 只拿目录（不含内容，几秒完成）
git clone https://github.com/Xinye25125763-cmd/kaogong-hub.git

# 连内容一起拉（340 MB，建议配代理）
git clone --recursive https://github.com/Xinye25125763-cmd/kaogong-hub.git

# 已经 clone 过，补拉某个分区
git submodule update --init 01-备考技能
```

## 同步上游更新

子模块钉在具体 commit 上，不会自动跟随上游。上游有新版时：

```bash
cd 02-行测真题
git fetch origin && git merge origin/main   # 或直接在网页点 Sync fork
```

然后在根目录 `git add 02-行测真题` 提交，把新指针记进目录。

## 说明

- 三个分区均为 fork，版权归原作者；`ERRRC/xingcezhenti` 原仓库未标注 LICENSE，
  `miss-mumu/developer2gwy` 为 `NOASSERTION`。个人存档使用没问题，再分发或商用前请先确认原作者授权。
- 目录名带序号是为了排序，想改直接改文件夹名并同步更新 `.gitmodules` 即可。
