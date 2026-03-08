---
title: PromQL
date: 2023-09-03
tags:
  - tools
  - promql
---

## PromQL 예제
### 특정 메트릭의 라벨 목록 추출하기
```
# max(메트릭 이름) by (라벨 이름)
max(node_exporter_build_info) by (service)
```
