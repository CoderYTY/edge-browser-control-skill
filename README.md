# Edge Browser Control Skill

这是给 Codex 用的配套 skill，让 Codex 在你说“操控 Edge 浏览器”“看我的标签页”“读取当前页面”“点击页面元素”等请求时，知道应该调用本机的 Edge 桥接命令。

## 搭配使用

这个仓库只提供 Codex 的调用说明和入口元数据；真正负责访问 Microsoft Edge 的扩展、Native Messaging host 和命令行工具在配套浏览器插件仓库里：

- 浏览器插件仓库：[CoderYTY/codex-edge-access-bridge](https://github.com/CoderYTY/codex-edge-access-bridge)

简单说：插件仓库负责“能访问 Edge”，本 skill 仓库负责“让 Codex 记得怎么访问 Edge”。两个需要搭配使用。

## 文件

- `SKILL.md`：Codex skill 主说明，包含连接检查、读取页面、点击、输入、截图和安全边界。
- `agents/openai.yaml`：给 Codex UI / agent 索引用的显示名、短描述和默认提示。

## 使用前提

先按插件仓库 README 安装并加载 Edge 扩展，确保 `Codex Edge Bridge` 控制台页显示 `connected`。然后把本仓库作为 skill 安装到 Codex 的 skills 目录中。

安装完成后，新会话里可以用类似这些说法触发：

```text
操控 Edge 浏览器，看看我有哪些标签页
访问我的 Edge，读取当前页面内容
打开网页并帮我点击登录按钮
```
