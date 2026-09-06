---
id: recipe_template_id
title: 菜谱名称
tags:
  - 批量备餐
  - 经典家常菜
prep_time_min: 15
cook_time_min: 30
servings: 4
equipment:
  - 炒锅

main_ingredients:
  - name: 主料名称
    amount: 500
    unit: g
    category: 生鲜肉类

side_ingredients:
  - name: 配料名称
    amount: 20
    unit: g
    category: 调味蔬菜

seasonings:
  - name: 调料名称
    amount: 15
    unit: ml
    category: 酱料调料
---

# {{title}}

```dataview
LIST WITHOUT ID "🏷️ 标签: " + file.tags
WHERE file.path = this.file.path
```

```dataview
LIST WITHOUT ID "⏱️ 预处理：" + prep_time_min + " 分钟 | 烹饪：" + cook_time_min + " 分钟 | 🍽️ 份量：" + servings + " 人份"
WHERE file.path = this.file.path
```

> 💡 **菜品特点**：简要描述口感、批量备餐储存建议与风味特征。

---

## 🥩 食材与调料

**🥩 主料**：
```dataview
LIST WITHOUT ID ing.name + " (" + ing.amount + ing.unit + ")"
WHERE file.path = this.file.path
FLATTEN main_ingredients AS ing
```

**🧄 配料**：
```dataview
LIST WITHOUT ID ing.name + " (" + ing.amount + ing.unit + ")"
WHERE file.path = this.file.path
FLATTEN side_ingredients AS ing
```

**🧂 调料**：
```dataview
LIST WITHOUT ID ing.name + " (" + ing.amount + ing.unit + ")"
WHERE file.path = this.file.path
FLATTEN seasonings AS ing
```

---

## 🥣 预处理

* **步骤一**：清洗,切块,浸泡或提前腌制说明。

---

## 👨‍🍳 烹饪步骤

1. **步骤一**：火候控制与下锅顺序。
2. **步骤二**：调味与收汁/出锅建议。
