# 第七章：配置参考

## 项目目录结构

创建项目后，项目目录的文件结构如下：

```
{项目名}/
├── project.json                 项目配置文件
├── characters/                  角色数据目录
│   └── {角色ID}/
│       ├── data.json            角色数据（属性/战斗配置/登场方式等）
│       ├── event.json           事件元数据（启用状态/附加项）
│       ├── Event/               事件块文件（每个事件一个 JSON）
│       ├── Unit/                战斗图标（小图）
│       ├── Unit_H/              战斗图标（大图）
│       ├── Figure/              立绘
│       ├── CG/                  事件 CG 图片
│       ├── Mating/              交配场景图
│       ├── Animated/            缩略图（自动生成）
│       ├── Icon/                头像图标
│       ├── Torture/             刑具图片
│       └── Voice/               角色语音
├── event_assets/                项目级共享事件资源
│   ├── Background/              共享背景图
│   ├── Figure/                  共享立绘
│   └── Voice/                   共享语音
└── export/                      导出输出目录（每次导出前清空）
```

## 事件

当前事件类别和子事件为预设，不可自建。具体事件列表见[事件编辑器](04_h5_event_editor.md)。

事件文件存放在 `characters/{角色ID}/Event/` 目录下，文件名格式为 `{事件ID}_{角色ID}.json`（如 `captured_mika.json`）。

## 块数据格式

事件文件中，块以 JSON 数组存储，每个元素为一行文本指令：

```json
{
  "event": [
    "background:bg_forest.webp",
    "name:Alice",
    "dialog:你好！",
    "",
    "CG:mika_01_1.webp",
    "sound:sound=slash_1 vol=0",
    "dialog:发生了什么？",
    ""
  ]
}
```

- 每个数组元素对应一个块
- 空字符串 `""` 表示等待点击（分页）
- 格式为 `指令:参数`，多参数用空格分隔的键值对

## 角色数据结构

角色数据存储在 `characters/{角色ID}/data.json`，主要包含以下顶级字段：

| 字段 | 说明 |
|------|------|
| translation | 角色名称翻译（chs/en/jp） |
| heroine_info | 角色属性（星级/领导力/元素等） |
| unit_info | 战斗配置（攻击方式/技能/装备） |
| unit_info_h | 战斗配置（敌方视角） |
| appearance | 登场方式（出场条件/位置/随从/速度） |
| brothel_info | 物品掉落概率列表 |
