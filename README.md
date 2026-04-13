# LangChain Streamlit Agent (SiliconFlow / OpenAI-compatible)

一个基于 **Streamlit + LangChain** 的对话式 Agent 示例：
- 支持对话记忆（`StreamlitChatMessageHistory`）
- 支持文件上传解析：PDF / Word / Excel
- 内置工具：获取当前时间、数学计算器
- 兼容不支持 function-calling 的模型：`TOOL_MODE="manual"`

## 运行环境
- Python 3.10+（建议 3.11+）

## 安装依赖
```bash
python -m venv .venv
# Windows PowerShell
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

## 配置（推荐 secrets.toml）
本项目的配置读取优先级：
1) 环境变量（`SILICONFLOW_*`）
2) `.streamlit/secrets.toml`
3) 项目根目录 `secrets.toml`

方式 A：`.streamlit/secrets.toml`（推荐，默认被 `.gitignore` 忽略）
```toml
[siliconflow]
api_key = "YOUR_KEY"
base_url = "https://api.siliconflow.cn/v1/"
model_name = "deepseek-ai/DeepSeek-R1-0528-Qwen3-8B"
temperature = 0
max_tokens = 4096
tool_mode = "manual" # "manual" | "native" | "none"
```

你也可以直接复制 `secrets.toml.example` 为 `secrets.toml` 或 `.streamlit/secrets.toml` 再填写密钥。

方式 B：环境变量（临时，仅当前终端会话）
```powershell
$env:SILICONFLOW_API_KEY="YOUR_KEY"
```

## 启动
```bash
streamlit run langchain_agent_app.py
```

## 小测试
```bash
python api_test.py
```
