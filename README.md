# llm-wiki-skills

Obsidian LLM Wiki 운영용 [Claude Code](https://claude.com/claude-code) 스킬 모음.

## 스킬

| 스킬 | 설명 |
|------|------|
| [`ingest`](./ingest/SKILL.md) | `raw/` 폴더의 소스(문서·아티클·논문)를 읽어 LLM Wiki로 편입 — 소스 요약 작성, 엔티티·개념 페이지 생성/갱신, MOC·index·log 갱신. 볼트의 `CLAUDE.md §6`을 실행 절차로 구체화. |

## 설치 (전역 스킬로 등록)

이 레포를 클론한 뒤, 각 스킬 디렉토리를 `~/.claude/skills/` 아래로 심볼릭 링크하면
모든 Claude Code 세션에서 인식된다 (세션 재시작 1회 필요).

```bash
git clone git@github.com:<USER>/llm-wiki-skills.git ~/Project/llm-wiki-skills
ln -s ~/Project/llm-wiki-skills/ingest ~/.claude/skills/ingest
```

이 레포가 단일 진실 원천이다. `~/.claude/skills/ingest`는 여기를 가리키는 링크이므로,
레포에서 편집·커밋하면 실제 스킬에 바로 반영된다.

## 구조

```
llm-wiki-skills/
└── ingest/
    └── SKILL.md   # frontmatter(name, description) + 절차
```
