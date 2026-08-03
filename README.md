# NEON DRIFT — 赛博朋克个人星系站

一个 Next.js (App Router) + React Three Fiber 打造的 3D 个人站点：银翼杀手 2049 风格星空、可交互行星导航、12 格情绪罗盘、3D 记忆长廊，全站 Web Audio 实时合成音效。

## 本地开发

```bash
npm install
npm run dev        # http://localhost:3213
```

## 静态导出

```bash
npm run build      # 产物输出到 out/（纯静态文件，可托管到任意静态空间）
npm run start      # 本地预览生产构建（需要先 build）
```

## 分享给别人看（两种方案）

### 方案 A：GitHub Pages（免费、永久公网地址）

1. 在 GitHub 新建一个仓库（例如 `neon-drift`）。
2. 把本项目代码推到该仓库的 `main` 分支：
   ```bash
   git remote add origin https://github.com/<你的用户名>/<仓库名>.git
   git push -u origin main
   ```
   > 默认分支名是 `main`。若你的仓库默认分支是 `master`，请同步修改 `.github/workflows/deploy.yml` 里的 `branches: [main]`。
3. 仓库 **Settings → Pages → Build and deployment → Source** 选择 **GitHub Actions**。
4. 推送后 Actions 会自动构建并部署，几分钟后得到地址：
   ```
   https://<你的用户名>.github.io/<仓库名>/
   ```
5. basePath 已自动处理（CI 里读取 `GITHUB_REPOSITORY`），无需手动改配置。

### 方案 B：CloudStudio 即时部署

把 `out/` 目录直接上传到 CloudStudio 静态空间即可获得公网链接，手机/电脑自适应。

## 自定义内容

改这几个文件即可替换文案与素材：

- `data/siteConfig.ts` — 个人简介、联系方式、站点标题
- `data/planetsData.ts` — 8 颗星球的名称、坐标、板块路由
- `data/sectorsData.ts` — 各板块的条目内容
- `data/emotionsData.ts` — 12 个情绪及其随笔
- `data/photosData.ts` + `public/photos/` — 摄影作品与 EXIF
