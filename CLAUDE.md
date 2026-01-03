# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

개발 생산성을 위한 CLI 유틸리티 스크립트 모음. 현재는 Git worktree 도구가 포함되어 있으며, 추후 다양한 도구가 추가될 예정. Bash 스크립트로 구성되어 별도 빌드 시스템 없음.

## Scripts

### gw - Worktree 생성
```bash
gw <branch-name>
```
- 현재 git 프로젝트 상위 디렉토리에 `{project}_{branch}` 형식으로 worktree 생성
- 브랜치 없으면 자동 생성, 있으면 재사용
- 생성 후 VSCode로 자동 오픈

### gwd - Worktree 삭제
```bash
gwd <branch-name>          # 단일 worktree 삭제
gwd -a, --all              # merge된 worktree만 일괄 삭제
gwd -a -f, --all --force   # 모든 worktree 강제 삭제
```
- Worktree와 연결된 브랜치 함께 삭제
- merge 여부 판단: `git branch --merged`, remote 브랜치 삭제 여부, squash/rebase merge 감지

## Installation

스크립트를 PATH에 추가하거나 심볼릭 링크 생성:
```bash
ln -s /path/to/tools/gw /usr/local/bin/gw
ln -s /path/to/tools/gwd /usr/local/bin/gwd
```

## Testing

테스트 프레임워크 없음. 수동 테스트:
```bash
# 권한 확인
chmod +x gw gwd

# gw 테스트
gw test-branch

# gwd 테스트
gwd test-branch
```

## Code Conventions

- Bash 스크립트: `set -e`로 에러 시 즉시 종료
- 색상 출력 함수: `error()`, `info()`, `warn()`
- 사용자 메시지는 한국어로 작성
