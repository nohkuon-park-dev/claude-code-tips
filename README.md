# Claude Code 꿀팁 모음

Claude Code를 제대로 활용하기 위한 검증된 팁, 워크플로우, 프롬프트, 도구 정리집.

---

## 파일 목록

| 파일 | 내용 |
|------|------|
| [01-setup.md](./01-setup.md) | CLAUDE.md 템플릿, MCP 설치, 스킬 설정 |
| [02-workflows.md](./02-workflows.md) | Plan→Do→Verify, Plan Mode, 멀티에이전트 팀 모드 |
| [03-prompts.md](./03-prompts.md) | 아첨 방지, ISO 아키텍트, 빠른 프롬프트 템플릿 |
| [04-cost-and-performance.md](./04-cost-and-performance.md) | 토큰 절약, 컨텍스트 관리, 사용량 추적 |
| [05-tools.md](./05-tools.md) | MCP 서버, 스킬 컬렉션, 스크래핑 도구 |

---

## 상황별 활용 가이드

| 상황 | 참고 파일 |
|------|----------|
| 새 프로젝트 시작 | `01-setup.md` → CLAUDE.md 템플릿 복붙, MCP 설치 |
| 기능 개발 전 | `02-workflows.md` → Plan→Do→Verify 루프 따라가기 |
| 중요한 결정 앞에 | `03-prompts.md` → 아첨 방지 프롬프트로 검증 |
| 요금이 너무 많이 나올 때 | `04-cost-and-performance.md` → 토큰 절약 습관 적용 |
| 새 도구가 필요할 때 | `05-tools.md` → MCP 목록에서 골라 설치 |

---

## 빠른 시작

```bash
# 1. 로그인
claude auth login

# 2. MCP 설치
claude mcp add --transport http context7 https://mcp.context7.com/mcp
claude mcp add --transport stdio playwright -- npx @playwright/mcp
claude mcp add --transport stdio github -e GITHUB_TOKEN=$(gh auth token) -- npx -y @modelcontextprotocol/server-github
claude mcp add --transport stdio memory -- npx -y @modelcontextprotocol/server-memory
claude mcp add --transport stdio sequential-thinking -- npx -y @modelcontextprotocol/server-sequential-thinking

# 3. 전역 CLAUDE.md 생성
touch ~/.claude/CLAUDE.md   # 본인 규칙 추가

# 4. 프로젝트별 설정
claude   # 실행 후 /init 으로 프로젝트 CLAUDE.md 자동 생성
```
