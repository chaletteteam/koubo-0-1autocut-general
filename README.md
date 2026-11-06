# 口播一键成片（通用版）

一个给 AI 剪辑助手用的 Workflow Skill：任何行业、任何文案的口播原片（raw 或已粗剪）丢进来，自动剪成 9:16 竖屏成片。

## 它会做什么

- **粗剪**：剪停顿、口癖、看稿穿帮、讲错重来（已粗剪的视频不动剪辑点）
- **变速**：整体 1.1 倍，音高不变
- **字幕**：超粗黑体白字 + 阴影，**只能一行**，按意思断句
- **花字**：白黄两色，按语义配动画（弹跳、砸入、金币、马克笔、翻牌等），紧贴字幕上方
- **全屏 MG**：复古撕纸拼贴风；讲到 Point 1/2/3、步骤、案例时自动做，同类内容同一套设计；人物在中间色带里，要点出现前放大、出现后缩到一侧，人物 / 文字 / 字幕互不遮挡
- **黑底圆框打字**：只用在一处关键提问句
- **音效**：按画面事件配不同音效（快门、提示音、冲击、鼓点等），都小过人声
- **BGM**：默认自动下载 Summit Regrace BGM，人声说话时自动压低
- **全程自动**：中途不提问；剪完才问 BGM 要不要换、建议补哪些素材

## 文件结构

```
SKILL.md                     # 主流程、参数、判断规则、禁止事项
references/components.md     # 组件说明（属性、位置、用法）
references/mg/               # Motion Graphic 组件（Remotion JSX）
  HuaZi.jsx                  # 花字
  StrikeText.jsx             # 删除线花字
  TypeLine.jsx               # 黑底圆框段的打字字幕
  MarkerText.jsx             # 马克笔高亮字（备用）
  collage-kit.jsx            # 撕纸 MG 共用组件
  collage-*.jsx              # 7 个撕纸 MG 版式
references/effects/
  flash-zoom-in.ts           # 开场闪白入场特效
```

## 使用方式

在支持 Workflow Skill 的 AI 剪辑环境（例如 ChatCut）里导入这个 skill，然后对 AI 说"帮我一键成片这条口播"，附上原片即可。

## 说明

- 默认 BGM 通过 SKILL.md 里的公开链接下载；链接失效时不加 BGM，剪完会请你上传。
- MG 配色与字体沿用「2nd Collage｜复古撕纸」风格（新青年体 + Archivo Black，四色）。
