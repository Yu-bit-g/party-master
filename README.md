# 派对大玩家 · Party Master

一个打开就能玩的线上派对小游戏合集：猜拳对战、疯狂骰子、真心话大冒险。纯前端单页应用，无需安装、无需注册。

在线试玩（Qoder Sites）：<https://party-master-ejzm6nqoes7.qoder.zone>

GitHub Pages 镜像：<https://yu-bit-g.github.io/party-master/>

> 本作品参加 2026 Qoder 高校创造力大赛（LifeHack 生活娱乐赛道），投稿材料见 [`submission/`](submission/)。

## 功能

- **猜拳对战**：双方同时出拳、确认后统一揭晓，三局两胜。
- **疯狂骰子**：可选 1–3 颗骰子，比较点数总和。
- **真心话大冒险**：8 格转盘随机抽取，内置 20 条题目。
- **实时联机**：通过 PeerJS + WebRTC 点对点连接，不经过游戏服务器转发对局数据。
- **AI 兜底**：3 秒内未匹配到真人时自动进入 AI 对战，随时可以玩。
- **成长系统**：胜场获得星星，累计升段；昵称、头像、段位保存在浏览器 LocalStorage。

## 本地运行

项目只有一个 `index.html`，不需要构建。由于使用了 WebRTC，建议通过本地 HTTP 服务打开，而不是直接双击文件：

```bash
python -m http.server 8080
```

然后访问 <http://localhost:8080>。

## 联机说明与限制

- 信令使用 PeerJS 公共云服务，对战数据走 WebRTC 点对点连接。
- 当前演示版为每个玩法使用固定房间号，**同一玩法同一时间只支持一对玩家**。如需多人房间，可自行把固定房间号改为随机房间码。
- 固定房间意味着在公开部署时，陌生人可能进入同一房间。对局中只交换昵称、头像和段位，不上传 LocalStorage 中的完整战绩。
- 页面通过 CDN 加载 Tailwind CSS 和 PeerJS，首次打开需要联网。

## 技术栈

- HTML5 + CSS3 + 原生 JavaScript
- Tailwind CSS（Play CDN）
- PeerJS 1.5.4（WebRTC 点对点连接）
- LocalStorage（本地成长数据）

## 项目结构

```text
.
├── index.html    # 全部页面、样式与游戏逻辑
├── README.md
├── LICENSE
└── .nojekyll     # GitHub Pages 静态托管
```

## 许可

本项目使用 [MIT License](LICENSE) 开源。
