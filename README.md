# TechEdict - 武林角色测试

> 用江湖的方式，测出你的技术团队角色。

一款将技术岗位人格化为中国武侠门派的趣味性格测试。回答 20 道江湖情境题，系统根据你的选择匹配最适合的技术角色 -- 从统御全局的「御剑阁主」(CTO) 到逍遥自在的「逍遥散人」(Fullstack)。

## 功能特色

- **12 种技术角色**：覆盖 CTO、PM、架构师、QA、DevOps、团队Leader、技术规划师、技术规范师、前端、后端、测试、全栈
- **20 道情境题目**：以武侠世界观包装的真实技术场景决策
- **6 维能力雷达图**：战略思维 / 沟通协调 / 架构设计 / 质量把控 / 执行效率 / 技术创新
- **Top 5 角色排名**：展示得分最高的 5 个匹配角色
- **角色档案卡片**：包含门派归属、武功秘籍、性格标签、经典语录
- **纯前端单文件**：零依赖部署，无后端，无数据库

## 技术栈

| 技术  | 说明  |
| --- | --- |
| HTML5 | 单文件应用（SPA） |
| CSS3 | 原生 CSS 动画 + 渐变 + 弹性布局 |
| JavaScript (ES6+) | 原生 JS，无框架依赖 |
| Canvas | 雷达图绘制 |
| Google Fonts | 马善政体 / 思源宋体 / 站酷小薇 |

## 本地运行

无需安装任何依赖，直接用浏览器打开即可：

```bash
# 方式一：直接打开
open index.html

# 方式二：本地 HTTP 服务器（推荐，避免字体跨域问题）
python3 -m http.server 8888
# 浏览器访问 http://localhost:8888
```

## Nginx 部署

```nginx
server {
    listen       8888;
    server_name  _;

    root /var/www/techedict-test;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

```bash
# 部署步骤
sudo mkdir -p /var/www/techedict-test
sudo cp index.html /var/www/techedict-test/
sudo nginx -t          # 检查配置
sudo systemctl reload nginx
```

访问 `http://<your-server-ip>:8888` 即可。

## 项目结构

```
techedict-test/
└── index.html          # 单文件应用（全部代码内联）
```

## 角色对照表

| 技术角色 | 武林身份 | 门派  | 武功秘籍 |
| --- | --- | --- | --- |
| CTO | 御剑阁主 | 御剑阁 | 乾坤御剑诀 |
| PM  | 传功长老 | 传功堂 | 七巧玲珑心经 |
| Architect | 天机阁主 | 天机阁 | 天罡北斗阵 |
| QA  | 执法堂主 | 执法堂 | 明镜止水诀 |
| DevOps | 机括阁主 | 机括阁 | 千机百变术 |
| Team Lead | 兵部尚书 | 兵部  | 点将录 |
| Tech Planner | 户部尚书 | 户部  | 精打细算功 |
| Standard | 礼部尚书 | 礼部  | 法度森严诀 |
| Frontend | 七秀弟子 | 七秀坊 | 飞花拈叶手 |
| Backend | 武当弟子 | 武当派 | 太极两仪功 |
| Tester | 少林弟子 | 少林寺 | 金钟罩铁布衫 |
| Fullstack | 逍遥散人 | 逍遥派 | 逍遥游 |

## License

MIT
