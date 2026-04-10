# LangChain Streamlit Agent（SiliconFlow / OpenAI-compatible）

这是一个基于 **Streamlit + LangChain** 的对话式 Agent 应用：
- 支持对话记忆（`StreamlitChatMessageHistory`）
- 支持文件上传解析：PDF / Word / Excel
- 内置工具：获取当前时间、数学计算器（并兼容不支持 function-calling 的模型：`TOOL_MODE="manual"`）

## 运行环境
- Python 3.10+（建议 3.11）

## 安装依赖
```bash
python -m venv .venv
# Windows PowerShell
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

## 启动
```bash
streamlit run langchain_agent_app.py
```

启动后在浏览器中使用侧边栏上传文件，并在聊天框输入问题即可。

## 配置（重要）
代码里 `Config` 使用了 `ChatOpenAI` 的 OpenAI 兼容参数（`api_key/base_url/model`）。

建议不要把真实 `API_KEY` 直接提交到 Git。更安全的做法是：
1. 把密钥放到环境变量（例如 `SILICONFLOW_API_KEY`）
2. 将 `langchain_agent_app.py` 里的 `Config.API_KEY` 改为读取环境变量（如需我来改，我可以在你确认后再改代码）

设置环境变量示例：
```bash
# Windows PowerShell（临时，仅当前终端会话）
$env:SILICONFLOW_API_KEY="YOUR_KEY"
```

## 常见问题
- 依赖缺失：请确认已执行 `pip install -r requirements.txt`
- 上传解析失败：确认安装了对应库（PDF/Word/Excel 的解析依赖见 `requirements.txt`）
