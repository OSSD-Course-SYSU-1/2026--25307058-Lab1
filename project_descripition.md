# 鸿蒙天气应用 - 工程代码解析文档

## 一、工程概述

本项目是一个基于 HarmonyOS 开发的天气应用，使用 ArkTS 语言编写，API 版本为 9+。
应用主要功能包括：获取天气数据、展示多个城市天气情况、天气图标渲染等。

## 二、工程结构

Weather-main/
├── AppScope/                    # 应用级配置
│   └── app.json5               # 应用配置文件
├── entry/                       # 主模块（Entry Module）
│   └── src/
│       └── main/
│           ├── ets/            # ArkTS 源代码
│           │   ├── entryability/   # 入口 Ability
│           │   │   └── EntryAbility.ets
│           │   └── pages/          # 页面文件
│           │       └── Index.ets
│           └── resources/      # 资源文件
│               ├── base/
│               │   ├── element/    # 颜色、字符串等常量
│               │   ├── media/      # 图片资源（天气图标）
│               │   └── profile/    # 页面配置
│               └── rawfile/        # 原始文件
├── build-profile.json5          # 构建配置
├── hvigorfile.ts               # 构建脚本
├── oh-package.json5            # 依赖配置
└── README.md                   # 项目说明


## 三、核心文件详解

### 1. EntryAbility.ets
- **路径**：`entry/src/main/ets/entryability/EntryAbility.ets`
- **功能**：应用入口 Ability，负责生命周期管理和页面加载
- **关键代码**：加载首页 `Index` 页面

### 2. Index.ets（主页面）
- **路径**：`entry/src/main/ets/pages/Index.ets`
- **功能**：天气应用主界面，展示天气信息
- **核心逻辑**：
  - 调用天气 API 获取数据
  - 解析 JSON 数据
  - 渲染 UI（温度、城市、天气图标）

### 3. 资源文件
- **天气图标**：`resources/base/media/` 目录下
  - `SunnyDay.png`（晴天）
  - `CloudyDay.png`（多云）
  - `RainyDay.png`（雨天）
  - 等
- **颜色/字符串常量**：`resources/base/element/` 目录下

## 四、数据流

1. **网络请求**：调用天气 API（如 OpenWeatherMap 或和风天气）
2. **数据解析**：JSON 解析为天气数据对象
3. **状态管理**：使用 `@State` 装饰器管理页面状态
4. **UI 渲染**：根据数据动态更新界面

## 五、技术栈

- **开发语言**：ArkTS（TypeScript 扩展）
- **UI 框架**：ArkUI（声明式 UI）
- **API 版本**：HarmonyOS API 9+
- **构建工具**：Hvigor

## 六、运行方式

1. 使用 DevEco Studio 打开工程
2. 配置 Remote Emulator 或 Local Emulator
3. 点击运行按钮，在模拟器中查看效果
