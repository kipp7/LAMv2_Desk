# LAMv2 Desk（Windows）

此仓库为山体滑坡监测预警平台的 Windows 桌面端（WPF + WebView2），并包含对应的前端 UI（Vite + React）。

## 目录

- `apps/desk`：前端 UI
- `apps/desk-win`：Windows 桌面壳

## 开发（本地联调）

1. 安装依赖（仓库根目录）：

   - `npm install`

2. 启动前端（端口 5174）：

   - `npm run dev`

3. 启动桌面端（指向 dev server）：

   - PowerShell（仓库根目录）：
     - `$env:DESK_DEV_SERVER_URL="http://localhost:5174/"; dotnet run --project .\apps\desk-win\LandslideDesk.Win\LandslideDesk.Win.csproj`

## 生产构建（本地静态资源）

1. 构建前端（生成 `apps/desk/dist`）：

   - `npm run build`

2. 发布桌面端（会把 `apps/desk/dist` 复制到输出目录的 `web/`）：

   - `dotnet publish .\apps\desk-win\LandslideDesk.Win\LandslideDesk.Win.csproj -c Release -r win-x64`

## 依赖

- Node.js >= 18
- .NET 8 SDK
- WebView2 Runtime（Win11 通常自带）

## 文档

- 工作记录：`docs/AI_WORKLOG.md`
- API 对接：`docs/API_INTEGRATION.md`

