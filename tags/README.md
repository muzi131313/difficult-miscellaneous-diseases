# 疾病标签系统

> 为每个疾病文档添加标准化标签，方便分类、搜索和筛选。

> ⚠️ **重要提示**：本内容仅供科普参考，不能替代专业医疗建议。请阅读仓库中的[免责声明](../DISCLAIMER.md)了解更多详情。

---

**最后更新**：2026-03-09

---

## 标签系统说明

### 目的

- **标准化分类**：统一疾病的分类标准
- **快速筛选**：按不同维度筛选疾病
- **便于搜索**：通过标签快速查找相关疾病
- **风险评估**：了解疾病的严重程度和紧急程度

### 使用方式

在疾病文档的顶部（免责声明后）添加 YAML 格式的标签块：

```markdown
---
tags:
  # 基础信息
  name: 疾病名称
  category: 分类
  
  # 严重程度
  severity: 轻度|中度|重度|致命
  emergency: true|false
  
  # 发病情况
  commonness: 罕见|少见|常见|高发
  onset: 急性|慢性|可急可慢
  
  # 发病人群
  age-group: 儿童|成年人|老年人|全年龄段
  gender-preference: 男性|女性|无差异
  
  # 系统分类
  system: 脑神经系统|消化系统|心血管系统|呼吸系统|内分泌系统|骨骼肌肉系统
  
  # 治疗方式
  treatment-surgery: true|false
  treatment-medication: true|false
  treatment-chronic: true|false
  
  # 预防等级
  prevention-level: 一级|二级|三级
  
  # 康复需求
  rehabilitation: true|false
  
  # 标签
  keywords: ["标签1", "标签2", "标签3"]
---
```

---

## 标签定义

### 基础信息标签

| 标签 | 说明 | 可选值 |
|------|------|--------|
| **name** | 疾病名称 | - |
| **category** | 疾病分类 | - |

### 严重程度标签

| 标签 | 说明 | 定义 |
|------|------|------|
| **severity** | 严重程度 | 轻度：症状轻微，生活质量影响小<br>中度：症状明显，影响生活<br>重度：症状严重，显著影响生活<br>致命：可危及生命 |
| **emergency** | 是否需要紧急处理 | true：需立即就医<br>false：可择期就诊 |

### 发病情况标签

| 标签 | 说明 | 定义 |
|------|------|------|
| **commonness** | 发病率 | 罕见：< 1/10,000<br>少见：1/1,000 - 1/10,000<br>常见：1/100 - 1/1,000<br>高发：> 1/100 |
| **onset** | 起病方式 | 急性：症状突然出现<br>慢性：症状逐渐发展<br>可急可慢：既可急性也可慢性 |

### 发病人群标签

| 标签 | 说明 | 可选值 |
|------|------|--------|
| **age-group** | 主要发病人群 | 儿童（0-18岁）<br>成年人（19-59岁）<br>老年人（≥60岁）<br>全年龄段 |
| **gender-preference** | 性别偏好 | 男性、女性、无差异 |

### 系统分类标签

| 标签 | 说明 | 可选值 |
|------|------|--------|
| **system** | 所属系统 | 脑神经系统<br>消化系统<br>心血管系统<br>呼吸系统<br>内分泌系统<br>骨骼肌肉系统 |

### 治疗方式标签

| 标签 | 说明 | 可选值 |
|------|------|--------|
| **treatment-surgery** | 是否需要手术治疗 | true、false |
| **treatment-medication** | 是否需要药物治疗 | true、false |
| **treatment-chronic** | 是否需要长期治疗 | true、false |

### 预防等级标签

| 标签 | 说明 | 定义 |
|------|------|------|
| **prevention-level** | 预防等级 | 一级：预防发病<br>二级：早发现早治疗<br>三级：预防并发症和复发 |

### 康复需求标签

| 标签 | 说明 | 可选值 |
|------|------|--------|
| **rehabilitation** | 是否需要康复 | true、false |

### 关键词标签

| 标签 | 说明 | 格式 |
|------|------|------|
| **keywords** | 关键词 | 数组格式，如：["高血压", "心血管"] |

---

## 标签示例

### 示例1：高血压

```markdown
---
tags:
  name: 高血压
  category: 心血管疾病
  
  severity: 中度
  emergency: false
  
  commonness: 高发
  onset: 慢性
  
  age-group: 成年人
  gender-preference: 无差异
  
  system: 心血管系统
  
  treatment-surgery: false
  treatment-medication: true
  treatment-chronic: true
  
  prevention-level: 一级
  
  rehabilitation: false
  
  keywords: ["高血压", "血压", "心血管", "卒中", "心肌梗死"]
---
```

### 示例2：脑梗

```markdown
---
tags:
  name: 脑梗
  category: 脑神经系统疾病
  
  severity: 重度
  emergency: true
  
  commonness: 常见
  onset: 急性
  
  age-group: 老年人
  gender-preference: 男性
  
  system: 脑神经系统
  
  treatment-surgery: false
  treatment-medication: true
  treatment-chronic: true
  
  prevention-level: 一级
  
  rehabilitation: true
  
  keywords: ["脑梗", "中风", "缺血性脑卒中", "脑梗死", "偏瘫"]
---
```

### 示例3：腹胀

```markdown
---
tags:
  name: 腹胀
  category: 消化系统疾病
  
  severity: 轻度
  emergency: false
  
  commonness: 常见
  onset: 可急可慢
  
  age-group: 全年龄段
  gender-preference: 女性
  
  system: 消化系统
  
  treatment-surgery: false
  treatment-medication: false
  treatment-chronic: false
  
  prevention-level: 一级
  
  rehabilitation: false
  
  keywords: ["腹胀", "消化不良", "肠易激综合征", "产气"]
---
```

### 示例4：冠心病

```markdown
---
tags:
  name: 冠心病
  category: 心血管疾病
  
  severity: 重度
  emergency: true
  
  commonness: 常见
  onset: 可急可慢
  
  age-group: 中老年人
  gender-preference: 男性
  
  system: 心血管系统
  
  treatment-surgery: true
  treatment-medication: true
  treatment-chronic: true
  
  prevention-level: 一级
  
  rehabilitation: true
  
  keywords: ["冠心病", "心绞痛", "心肌梗死", "冠心病", "心血管"]
---
```

---

## 已标记文档列表

| 文档 | 严重程度 | 紧急 | 发病率 | 起病 | 主要人群 |
|------|---------|------|--------|------|---------|
| [高血压](../cardiovascular/hypertension.md) | 中度 | false | 高发 | 慢性 | 成年人 |
| [冠心病](../cardiovascular/coronary-artery-disease.md) | 重度 | true | 常见 | 可急可慢 | 中老年人 |
| [脑梗](../cerebral-infarction/README.md) | 重度 | true | 常见 | 急性 | 老年人 |
| [腹胀](../digest/bloating.md) | 轻度 | false | 常见 | 可急可慢 | 全年龄段 |
| [便秘](../digest/constipation.md) | 轻度 | false | 常见 | 可急可慢 | 全年龄段 |

---

## 标签使用场景

### 1. 按严重程度筛选

```markdown
## 轻度疾病（症状轻微，生活质量影响小）
- [腹胀](../digest/bloating.md)
- [便秘](../digest/constipation.md)

## 中度疾病（症状明显，影响生活）
- [高血压](../cardiovascular/hypertension.md)

## 重度疾病（症状严重，显著影响生活）
- [冠心病](../cardiovascular/coronary-artery-disease.md)
- [脑梗](../cerebral-infarction/README.md)
```

### 2. 按紧急程度筛选

```markdown
## 需要紧急处理（立即就医）
- [冠心病](../cardiovascular/coronary-artery-disease.md) 🚨 心肌梗死
- [脑梗](../cerebral-infarction/README.md) 🚨 中风

## 可择期就诊
- [高血压](../cardiovascular/hypertension.md)
- [腹胀](../digest/bloating.md)
- [便秘](../digest/constipation.md)
```

### 3. 按发病率筛选

```markdown
## 高发疾病（> 1/100）
- [高血压](../cardiovascular/hypertension.md)（2.9亿患者）
- [冠心病](../cardiovascular/coronary-artery-disease.md)（1100万患者）
- [脑梗](../cerebral-infarction/README.md)（1300万患者）

## 常见疾病（1/100 - 1/1,000）
- [腹胀](../digest/bloating.md)（发生率20%-30%）
- [便秘](../digest/constipation.md)
```

### 4. 按人群筛选

```markdown
## 老年人常见疾病
- [脑梗](../cerebral-infarction/README.md)
- [冠心病](../cardiovascular/coronary-artery-disease.md)

## 全年龄段常见疾病
- [腹胀](../digest/bloating.md)
- [便秘](../digest/constipation.md)
```

### 5. 按康复需求筛选

```markdown
## 需要康复的疾病
- [脑梗](../cerebral-infarction/README.md) - 神经功能康复
- [冠心病](../cardiovascular/coronary-artery-disease.md) - 心脏康复

## 无需康复的疾病
- [高血压](../cardiovascular/hypertension.md)
- [腹胀](../digest/bloating.md)
- [便秘](../digest/constipation.md)
```

---

## 标签管理工具

### 添加标签到文档

**步骤：**
1. 打开疾病文档
2. 在免责声明后添加 YAML 标签块
3. 根据疾病特点填写标签
4. 提交修改

### 提取标签信息

如果需要从文档中提取标签信息用于分析或统计，可以使用以下 Python 脚本：

```python
import yaml
import re
from pathlib import Path

def extract_tags(md_file):
    """从 Markdown 文件中提取标签"""
    content = md_file.read_text(encoding='utf-8')
    
    # 查找 YAML 标签块
    match = re.search(r'---\n(.*?)\n---', content, re.DOTALL)
    if not match:
        return None
    
    yaml_content = match.group(1)
    
    # 如果包含 tags，提取 tags 部分
    tags_match = re.search(r'tags:(.*?)\n---', content, re.DOTALL)
    if tags_match:
        yaml_content = tags_match.group(0).replace('---', '')
    
    try:
        tags = yaml.safe_load(yaml_content)
        return tags
    except yaml.YAMLError as e:
        print(f"Error parsing YAML: {e}")
        return None

# 使用示例
doc_path = Path('cardiovascular/hypertension.md')
tags = extract_tags(doc_path)
if tags:
    print(tags)
```

---

## 标签规范

### 格式要求

1. **YAML 格式**：使用标准 YAML 语法
2. **缩进**：使用 2 个空格缩进
3. **布尔值**：使用 true/false（小写）
4. **字符串**：加引号（单引号或双引号）
5. **列表**：使用 `-` 开头

### 命名规范

1. **疾病名称**：使用中文标准名称
2. **分类**：使用"系统+疾病"格式
3. **关键词**：使用中文名称，避免缩写

### 一致性要求

1. **相同疾病，相同标签**：同一疾病在不同文档中使用相同的标签
2. **标签定义一致**：按照本文档的定义使用标签
3. **更新同步**：文档内容更新时，同步更新标签

---

## 更新日志

- **2026-03-09**：创建疾病标签系统
  - 定义标签系统结构
  - 提供标签使用示例
  - 创建标签参考文档
  - 列出已标记文档

---

## 互动与反馈

如果您对标签系统有任何建议或发现问题，欢迎：
1. 提交 [Issue](../../issues)
2. 提交 [Pull Request](../../pulls)

---

**再次提醒**：本系统仅供分类和检索参考，不能替代专业医疗建议。
