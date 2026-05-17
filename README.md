
# MindCare Multi-Agent 心理支持系统

一个基于多 Agent 协作的 AI 心理支持平台，用于情绪疏导、风险评估、长期陪伴与资源推荐。

## 项目核心痛点

当前心理咨询与情绪支持场景中存在以下问题：

1. 用户情绪表达碎片化，传统单 Agent 难以持续追踪上下文。
2. 用户可能同时存在情绪问题、压力问题、学习问题、人际问题，需要不同角色协同分析。
3. 单模型容易出现建议泛化、缺少长期记忆与风险感知。
4. 高危内容（自伤、自杀倾向）缺乏实时升级机制。
5. 心理咨询资源稀缺，无法做到 24 小时低成本陪伴。

本项目通过多 Agent 协作实现：
- 情绪识别
- 风险评估
- CBT 引导
- 长期记忆
- 干预升级
- 个性化资源推荐

---

## 多 Agent 架构

### 1. Emotion Agent（情绪识别）
提取：
- 情绪类别
- 压力来源
- 情绪强度

### 2. Risk Agent（风险评估）
检测：
- 自伤倾向
- 极端语言
- 长期抑郁风险

### 3. CBT Agent（认知行为疗法引导）
使用 CBT 模板进行：
- 自动认知纠偏
- 情绪重构
- 行为建议

### 4. Memory Agent（长期记忆）
记录：
- 用户长期情绪趋势
- 高频压力事件
- 历史咨询摘要

### 5. Resource Agent（资源推荐）
推荐：
- 冥想
- 呼吸训练
- 睡眠建议
- 校园/社会心理热线

### 6. Supervisor Agent（总控调度）
负责：
- Agent 调度
- 长链推理
- 输出融合
- 安全审查

---

## 核心逻辑流

用户输入
    ↓
Supervisor Agent
    ↓
Emotion Agent → 情绪标签
    ↓
Risk Agent → 风险等级
    ↓
CBT Agent → 心理支持建议
    ↓
Memory Agent → 更新长期状态
    ↓
Resource Agent → 个性化资源
    ↓
Supervisor 汇总最终回复

当 Risk Agent 判断为 HIGH 时：
- 自动触发安全干预
- 输出热线资源
- 建议联系专业人员

---

## 技术栈

- FastAPI
- OpenAI API
- Python
- Multi-Agent Orchestration
- JSON Memory Store

---

## 启动

```bash
pip install -r requirements.txt
uvicorn app:app --reload
```

---

## API

POST /chat

请求：

```json
{
  "user_id": "u001",
  "message": "最近压力特别大"
}
```

---

## 适用场景

- 校园心理支持
- 企业员工关怀
- AI 情绪陪伴
- 心理健康 SaaS
- 智能咨询助手

