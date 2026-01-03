# tools

개발 생산성을 위한 CLI 유틸리티 스크립트 모음.

## 현재 포함된 도구

### Git Worktree 관리
- **gw** - Git worktree 생성 및 VSCode 오픈
- **gwd** - Git worktree 삭제 (단일/일괄)

## 설치

스크립트를 PATH에 추가하거나 심볼릭 링크 생성:
```bash
ln -s /path/to/tools/gw /usr/local/bin/gw
ln -s /path/to/tools/gwd /usr/local/bin/gwd
```

## 사용법

```bash
# Worktree 생성
gw feature-branch

# Worktree 삭제
gwd feature-branch

# merge된 worktree 일괄 삭제
gwd -a

# 모든 worktree 강제 삭제
gwd -a -f
```

## 추후 추가 예정

다양한 개발 유틸리티 도구들이 추가될 예정입니다.
