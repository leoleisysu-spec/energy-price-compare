# energy-price-compare

能源价格查询与热值换算 Agent Skill：将查询到的能源价格汇总为比较表格，按各能源标准低位发热量统一换算为「人民币元/MJ」，并可乘 35 MJ/m³ 折算为「相当于XX元/方气」与天然气同口径比较；表格末尾注明所用换算热值。

## 触发条件
用户**单纯需要查询能源价格**（动力煤、LPG、LNG、柴油、汽油、氢气、天然气等，含期货与区域市场/零售价）时使用。

## 禁止条件
能源价格查询只是某个较大任务（研究报告、项目方案、财务测算、业务分析等）的一个方面时，**不自动触发**本技能。

## 安装
```bash
git clone https://github.com/leoleisysu-spec/energy-price-compare.git
```
将仓库内的内容（SKILL.md 与 references/ 文件夹）放入 Agent 环境的 `workspace/.user_skills/energy-price-compare/` 目录，重启会话后即可被自动加载。

## 功能
- 汇总能源价格比较表格（品种、口径、原始价格、数据日期/来源）
- 按标准低位发热量统一换算为元/MJ，全部换算用计算工具完成
- 与天然气比较时：元/MJ × 35 MJ/m³ = 相当于元/方气，并给出当地管道气价作参照
- 表格末尾注明所用换算热值（动力煤 23.03 MJ/kg、LPG 45.22 MJ/kg、LNG 50.0 MJ/kg、0# 柴油 35.8 MJ/L、氢气 120 MJ/kg、天然气基准 35 MJ/m³）

详细换算参考见 `references/calorific-values.md`。
