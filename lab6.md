# Git #1 Lecture Note (Week 6)

## 1. 버전 관리란?
- 소프트웨어 개발이나 문서 작업 시 변경 이력을 관리하고 협업을 효율적으로 수행하기 위한 시스템입니다.
- 단순히 파일 복사로 관리하는 것은 비효율적입니다.

예시:
```
프로젝트_최종.txt
프로젝트_최종_수정1.txt
프로젝트_최종_진짜최종.txt
```
- 이런 식으로 파일이 많아지면 버전 관리가 어렵습니다.

## 2. 버전 관리 시스템의 종류
- **Local VCS**: 개인 PC 내에서 버전 관리 (예: RCS)
- **Centralized VCS**: 중앙 서버에서 관리 (예: SVN)
- **Distributed VCS**: 각 사용자가 전체 저장소를 복제 (예: Git)

## 3. Git의 기본 개념
- Git은 데이터를 **변경 이력(changes)** 대신 **스냅샷(snapshot)** 형태로 저장합니다.
- 효율적인 복원과 버전 추적이 가능합니다.

## 4. Git의 3가지 상태
| 상태 | 설명 |
|------|------|
| Modified | 파일이 수정되었지만 아직 스테이징되지 않음 |
| Staged | 커밋 준비 완료 (스테이징 영역에 있음) |
| Committed | 변경 사항이 로컬 저장소에 반영됨 |

## 5. Git 설치
- **Windows:** https://git-scm.com/download/win  
- **Mac:** https://git-scm.com/download/mac  
- **Linux (Debian 계열):**
```
sudo apt install git
```

## 6. Git 설정 (처음 한 번만)
Git 설정은 3단계로 구성됩니다.

| 구분 | 옵션 | 적용 범위 | 파일 경로 |
|------|------|-----------|------------|
| System | --system | 모든 사용자 | /etc/gitconfig |
| Global | --global | 현재 사용자 | ~/.config/git/config |
| Local | --local | 현재 저장소 | .git/config |

> 우선순위: System → Global → Local

## 7. 기본 명령어 정리

### 저장소 초기화
```
git init
```

### 상태 확인
```
git status
```

### 파일 추가 (Staging)
```
git add [파일명]
```
또는 모든 파일 추가:
```
git add .
```

### 스테이징 해제
```
git rm --cached [파일명]
```

### .gitignore 설정
무시할 파일이나 폴더를 지정합니다.
```
*.log
__pycache__/
node_modules/
```

### 커밋 생성
```
git commit -m "커밋 메시지"
```

### 브랜치 이름 변경
```
git branch -m [새로운_브랜치명]
```

## 8. 요약
- Git은 협업과 버전 관리를 위한 필수 도구입니다.
- 기본 흐름: **수정 → 스테이징 → 커밋**
- 자주 사용하는 명령어를 숙지합시다.
