# llm-wiki-skills

Obsidian LLM Wiki 운영용 [Claude Code](https://claude.com/claude-code) 스킬 모음.

## 스킬

| 스킬 | 설명 |
|------|------|
| [`ingest`](./ingest/SKILL.md) | `raw/` 폴더의 소스(문서·아티클·논문)를 읽어 LLM Wiki로 편입 — 소스 요약 작성, 엔티티·개념 페이지 생성/갱신, MOC·index·log 갱신. 볼트의 `CLAUDE.md §6`을 실행 절차로 구체화. |
| [`tag`](./tag/SKILL.md) | `raw/` 폴더에 쌓인 파일에 그 파일이 무엇에 관한 것인지 주제 태그를 frontmatter에 부여 — 관리 태그 레지스트리(`_tags.md`) 기반. wiki 승격·파일 이동/삭제 없이 frontmatter만 수정. 권장 순서는 tag → ingest. |
| [`lint`](./lint/SKILL.md) | 볼트 건강검진 — broken link 자동 재연결, frontmatter 자동 보강, stale 삭제 결정 요청, orphan 연결 제안. `raw/`는 수정하지 않고, 모든 자동수정은 리포트 "수정됨"에 기록. |

## 설치 (전역 스킬로 등록)

이 레포를 클론한 뒤, 각 스킬 디렉토리를 `~/.claude/skills/` 아래로 심볼릭 링크하면
모든 Claude Code 세션에서 인식된다 (세션 재시작 1회 필요).

```bash
git clone git@github.com:<USER>/llm-wiki-skills.git ~/Project/llm-wiki-skills
ln -s ~/Project/llm-wiki-skills/ingest ~/.claude/skills/ingest
ln -s ~/Project/llm-wiki-skills/tag    ~/.claude/skills/tag
ln -s ~/Project/llm-wiki-skills/lint   ~/.claude/skills/lint
```

이 레포가 단일 진실 원천이다. `~/.claude/skills/ingest`는 여기를 가리키는 링크이므로,
레포에서 편집·커밋하면 실제 스킬에 바로 반영된다.

## 구조

```
llm-wiki-skills/
├── ingest/
│   └── SKILL.md   # frontmatter(name, description) + 절차
├── tag/
│   └── SKILL.md
└── lint/
    └── SKILL.md
```
