# heart-driven-robot

一个以 Python 为主的微信/微信群问答机器人项目，核心功能包括：

- 自动监听指定微信群消息。
- 提取以指定关键词开头的问题内容。
- 调用阿里云百炼（DashScope）的智能问答服务进行回答。
- 自动回复结果，并支持消息级与问题级去重。

## 项目特点

- **关键词触发**：默认监听以“#举手”开头的问题。
- **灵活配置**：通过环境变量与代码内置配置快速修改运行参数。
- **智能问答**：集成阿里云百炼智能问答服务。
- **多级去重**：避免重复处理消息或回答相同问题。

## 快速开始

### 环境准备

1. 克隆仓库：

   ```bash
   git clone https://github.com/kobeMichael2324/heart-driven-robot.git
   cd heart-driven-robot
   ```

2. 创建虚拟环境并安装依赖：

   ```bash
   python -m venv venv
   source venv/bin/activate   # macOS / Linux
   venv\Scripts\activate      # Windows
   pip install -r requirements.txt
   ```

3. 配置环境变量：

   创建 `.env` 文件，填写阿里云百炼 API Key：

   ```env
   DASHSCOPE_API_KEY=你的_api_key
   ```

4. 启动程序：

   ```bash
   python newmain.py
   ```

### 项目文件结构

- `newmain.py`：主程序，监听微信群消息并调用问答服务。
- `requirements.txt`：依赖库清单。
- `.env`：存放环境变量，比如 DashScope API Key。

## 依赖

- Python 3.8 或更高版本。
- 第三方库：
  - wxauto4
  - python-dotenv
  - dashscope
  - requests

## 配置说明

- **目标群聊名称**：通过 `TARGET_GROUP_NAME` 参数设置监听的群聊名称。
- **关键词触发**：通过 `TRIGGER_PREFIX` 自定义消息触发关键词（默认 `#举手`）。
- **百炼 API**：通过 `.env` 文件配置 `DASHSCOPE_API_KEY`。

## 注意事项

- 需确保微信客户端已登录，并与 wxauto4 版本兼容。
- 仅支持在与目标群聊名称匹配的群中触发问答。

## 许可

MIT License.