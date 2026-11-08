# zhangkui-plugins

个人 Claude 插件 marketplace,用于在 Claude 桌面应用(chat / Cowork)和 Claude Code CLI 之间共用同一套插件。

## 包含的插件

| 插件 | 说明 |
| --- | --- |
| `arkcli-skills` | 火山引擎方舟 CLI (arkcli) 技能集,共 26 个技能:模型查询、推理接入点、精调训练、多模态理解、计费、套餐管理等 |

## 目录结构

```
.claude-plugin/marketplace.json      # marketplace 定义
plugins/arkcli-skills/
  .claude-plugin/plugin.json         # 插件元数据
  skills/arkcli-*/SKILL.md           # 26 个技能
```

## 在桌面端安装(chat / Cowork)

1. 打开 Claude 桌面应用,进入 Cowork(或任意对话)→ 左侧 **Customize → Plugins**
2. 点 **Add → Add marketplace**,填入 `你的GitHub用户名/zhangkui-plugins`
3. 在列表中找到 `arkcli-skills`,点安装

## 在 Claude Code CLI 安装(可选)

```
/plugin marketplace add 你的GitHub用户名/zhangkui-plugins
/plugin install arkcli-skills@zhangkui-plugins
```

注意:如果你本机 `~/.claude/skills` 里已经有 arkcli 安装的同名技能,再装这个插件会造成同名技能重复,CLI 端一般**不需要**装,保持本地技能即可。

## 更新流程

1. 把新版技能从 `%USERPROFILE%\.claude\skills\arkcli-*` 复制回 `plugins/arkcli-skills/skills/`
2. 修改两处 `version`(marketplace.json 与 plugin.json)后提交推送
3. 桌面端在 Plugins 页点更新即可

## 版权说明

`arkcli-skills` 的内容来自火山引擎方舟 CLI(arkcli)官方分发的技能包,版权归原权利人所有。本仓库仅用于个人在不同工具间同步同一套技能,如需公开分发请自行确认授权。
