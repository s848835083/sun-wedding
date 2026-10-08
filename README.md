# 孙门盛宴 · 微信请柬

两页 H5：第 1 页短剧海报（头像），第 2 页联姻公告 + 回执凭证。纯静态，无外部依赖。

```
index.html        页面本体（文案直接改这里）
photos/groom.jpg  新郎头像（360×360，已从合照裁好）
photos/bride.jpg  新娘头像
bgm.mp3           背景音乐：《囚笼》— 爱在墨尔本（汽水音乐试听片段 60 秒，版权归原作者）
pay-wechat.png    微信收款码（自备；缺失时「随份子」按钮自动隐藏）
```

## 常改的地方
- 倒计时时刻：`index.html` 里搜 `WEDDING_AT`
- 场馆：搜 `绝密，确定后在本页更新`
- 背景音乐：放一个 `bgm.mp3` 到本目录。建议截 1–2 分钟、128kbps、< 3MB，压缩命令：
  `ffmpeg -i 原曲.mp3 -t 120 -b:a 128k -ac 2 bgm.mp3`

- 份子钱：微信 → 我 → 服务 → 收付款 → 二维码收款 → 保存收款码，图片改名 `pay-wechat.png` 放到本目录

## 本地预览
`python -m http.server 8765` 后打开 http://localhost:8765

## 发布（GitHub Pages）
1. GitHub 新建一个 public 仓库（如 `wedding`）
2. 把本目录的文件推上去
3. 仓库 Settings → Pages → Branch 选 `main` / root → Save
4. 一两分钟后得到 `https://<用户名>.github.io/wedding/`，复制发微信即可
