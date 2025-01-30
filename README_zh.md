---
title: "CoT-Lab: 人机协同思考实验室"
emoji: "🤖"
colorFrom: "blue"
colorTo: "gray"
sdk: "gradio"
python_version: "3.13"
sdk_version: "5.13.1"
app_file: "app.py"
models:
  - "deepseek-ai/DeepSeek-R1"
tags:
  - "写作助手"
  - "多语言"
license: "mit"
---

# CoT-Lab: 人机协同思考实验室
[Huggingface空间 🤗](https://huggingface.co/spaces/Intelligent-Internet/CoT-Lab) | [GitHub仓库 🌐](https://github.com/Intelligent-Internet/CoT-Lab-Demo)
[English README](README.md)

**通过同步人类与AI的思考过程，实现深层次的认知对齐**  
在一轮对话中跟随、学习、迭代思维链

## 🌟 项目介绍
CoT-Lab是一个探索人机协作新范式的实验性界面，基于**认知负荷理论**和**主动学习**原则，致力于探索人与AI的"**思考伙伴**"关系。

- 🧠 **认知同步**  
  调节AI输出速度，匹配不同场景下的人类信息处理速度匹配
- ✍️ **思维编织**  
  人类主动参与AI的思维链

** 探索性实验项目，正在积极开发中，欢迎讨论与反馈！ **

## 🛠 使用指南
### 基本操作
1. **设置初始提示**  
   在输入框描述您的问题（例如"解释量子计算基础"）

2. **调整认知参数**  
   - ⏱ **思考同步速度**：词元/秒 - 5:朗读, 10:跟随, 50:跳读
   - 📏 **人工思考节奏**：每X段落自动暂停（默认关闭 - 推荐主动学习场景使用）

3. **交互工作流**  
   - 点击`生成`开始协同思考，跟随思考过程
   - AI暂停时可编辑推理过程 - 或随时使用`Shift+Enter`暂停AI输出，进入思考、编辑模式
   - 思考、编辑后，使用`Shift+Enter`交还控制权给AI

## 🧠 设计理念
- **认知负荷优化**  
  信息组块化(Chunking)适配工作记忆限制，序列化信息呈现降低视觉搜索带来的认知负荷

- **主动学习增强**  
  直接操作思维链，促进深度认知投入

- **分布式认知**  
  探索人机携作的问题解决范式

## 📥 安装部署
如希望使用本地部署的大语言模型，您（暂时）需要克隆本项目并在本地运行。
因近期DeepSeek官方API不稳定，我们建议暂时使用第三方API供应商作为替代方案，或者使用本地部署的R1-Distilled模型进行实验。  

**环境要求**：Python 3.11+ | 有效的[Deepseek API密钥](https://platform.deepseek.com/) 或其他OpenAI SDK兼容的API接口。 

```bash
# 克隆仓库
git clone https://github.com/Intelligent-Internet/CoT-Lab-Demo
cd CoT-Lab

# 安装依赖
pip install -r requirements.txt

# 配置环境
API_KEY=sk-****
API_URL=https://api.deepseek.com/beta
API_MODEL=deepseek-reasoner

# 启动应用
python app.py
```

## 📄 许可协议
MIT License © 2024 [ii.inc]

## Contact
yizhou@ii.inc (Dango233)