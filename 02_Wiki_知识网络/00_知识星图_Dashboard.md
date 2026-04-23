# 🌌 知识星图 (PKB Dashboard)

```dataview
TABLE noteType as 类型, infoValue as 价值, infoDensity as 密度
FROM "02_Wiki_知识网络"
WHERE file.name != this.file.name
SORT file.mtime DESC
```
