---
title: kubectl 명령어
date: 2023-08-29
tags:
  - tools
  - kubectl
---

## 예제
### 전체 네임스페이스의 Pod 중 재시작을 한번 이상 한 Pod 찾기
```bash
> k get po -A | awk '$5>0'
```

### 특정 노드에 실행중인 Pod 출력
```bash
> k get po -o wide -A --field-selector spec.nodeName=노드이름
```

### 노드의 리소스 사용률 확인
```bash
# resource-capacity 명령은 krew로 설치
> k resource-capacity --sort cpu.request --util --node-labels woowa.in/role=eks-log-rg-private
```

### 사용하지 않는 PVC 삭제하기
```bash
> kubectl describe -A pvc | grep -E "^Name:.*$|^Namespace:.*$|^Used By:.*$" | grep -B 2 "<none>" | grep -E "^Name:.*$|^Namespace:.*$" | cut -f2 -d: | paste -d " " - - | xargs -n2 bash -c 'kubectl -n ${1} delete pvc ${0}'
```

### 노드의 Pod를 다른 노드로 이동시키기
```bash
> k drain --ignore-daemonsets --delete-local-data 노드이름
```
