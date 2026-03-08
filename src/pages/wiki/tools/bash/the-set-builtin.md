---
title: 셸의 내장 기능 set
date: 2023-09-07
tags:
  - tools
  - bash
  - set-builtin
---

셸이 동작하는 방식을 조절할 때 내장 기능 `set`을 사용한다. `set`은 Bash 매뉴얼에서 별도의 섹션을 할애할 정도로 복잡한 설정을 가지고 있다. 

## 사용법
```
set [-abefhkmnptuvxBCEHPT] [-o option-name] [--] [-] [argument …]
set [+abefhkmnptuvxBCEHPT] [+o option-name] [--] [-] [argument …]
```

set은 두가지 기능이 있다. `set -e -x`와 같은 옵션 설정 기능과 `set 11 22 33`과 같은 po

## 옵션

### -e | errexit
스크립트 실행 중에 명령이 0이 아닌 상태를 반환하면(즉, 에러로 종료하면) 즉시 종료한다.

### -x | xtrace
명령 실행전에 매개변수 확장, 명령치환, 산술 확장이 완료된 결과를 보여준다. 디버깅에 유용하게 사용할 수 있다.

## 참고
* https://www.gnu.org/software/bash/manual/html_node/The-Set-Builtin.html
