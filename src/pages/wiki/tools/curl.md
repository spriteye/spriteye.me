---
title: curl 명령어
date: 2021-12-30
tags:
  - tools
  - curl
---

## 예제
### 응답 시간 확인하기
```bash
> curl v2.wttr.in/Seoul -w "\n소요시간: %{time_starttransfer}초"
```
