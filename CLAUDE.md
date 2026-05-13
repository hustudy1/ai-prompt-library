# CLAUDE.md
# IT Technical Prompt Library

Claude Code 실행 시 이 파일을 자동으로 읽어 프로젝트 컨텍스트를 유지합니다.
IT 기술 전 도메인에 공통으로 적용되는 행동 기준 및 출력 형식을 정의합니다.
도메인 특화 내용은 각 도메인 폴더의 system-prompts 파일을 작업 시 직접 참조합니다.

---

## 📂 프로젝트 구조

```
ai-prompt-library/
├── CLAUDE.md                                                    ← 공통 기초 (현재 파일, 자동 로드)
│
├── bigdata-platform/
│   └── system-prompts/bigdata-platform-prompts.md              ← Hadoop, Spark, Trino, Kafka 등
│
├── infra/
│   └── system-prompts/infra-prompts.md                         ← Docker, K8s, CI/CD, 모니터링
│
├── db/
│   └── system-prompts/db-prompts.md                            ← RDBMS, NoSQL, 쿼리 최적화
│
└── ai/
    └── system-prompts/ai-prompts.md                            ← LLM, 프롬프트 엔지니어링, MLOps
```

---

## 🤖 공통 행동 기준

1. 모든 기술 답변은 공식 문서(1차 출처)를 기반으로 작성한다.
2. 답변 시 공식 문서 링크 또는 출처(문서명, 버전, 섹션)를 반드시 명시한다.
3. 공식 문서로 확인되지 않은 정보는 추측임을 명확히 표시하고 문서 확인을 안내한다.
4. 기술명 및 API 사용 시 버전을 반드시 명시한다.
5. Deprecated된 방법은 ⚠️ Deprecated 경고 후 최신 방법으로 안내한다.
6. 불확실한 설정값, API, 명령어, 버전 호환성을 임의로 생성하지 않는다.

---

## 📋 공통 출력 형식

- 일반 답변:      [설명 → 예시 → 출처]
- 아키텍처 답변:  [구조 설명 → 기술 비교표 → 트레이드오프 → 출처]
- 코드/쿼리 답변: [목적 → 코드(주석 포함) → 성능 고려사항 → 출처]
- 트러블슈팅:     [오류 원인 → 즉시 조치 → 근본 해결 → 재발 방지 → 출처]
- 한국어로 답변한다.

---

## 🔍 트러블슈팅 공통 형식

```
[오류 원인]   공식 문서 / Known Issue / 릴리즈 노트 기반 원인 분석
[즉시 조치]   당장 적용 가능한 명령어 / 설정 예시
[근본 해결]   변경 전 → 변경 후 설정 예시 포함
[재발 방지]   모니터링 포인트 및 예방 조치
[출처]        공식 문서 링크
```

---

## 📌 도메인별 프롬프트 참조 가이드

| 작업 도메인 | 참조 파일 |
|---|---|
| Bigdata (Hadoop, Spark, Trino, Kafka 등) | @bigdata-platform/system-prompts/bigdata-platform-prompts.md |
| 인프라 (Docker, K8s, CI/CD, 모니터링) | @infra/system-prompts/infra-prompts.md |
| 데이터베이스 (RDBMS, NoSQL, 쿼리 최적화) | @db/system-prompts/db-prompts.md |
| AI/ML (LLM, 프롬프트 엔지니어링, MLOps) | @ai/system-prompts/ai-prompts.md |

복합 도메인 작업 시 관련 파일을 복수 참조한다.

---

## 💡 사용 방법

### 단일 도메인 작업
```
@bigdata-platform/system-prompts/bigdata-platform-prompts.md 참고해서 Spark OOM 해결해줘
@infra/system-prompts/infra-prompts.md 참고해서 K8s Pod CrashLoopBackOff 분석해줘
@db/system-prompts/db-prompts.md 참고해서 PostgreSQL 슬로우 쿼리 최적화해줘
@ai/system-prompts/ai-prompts.md 참고해서 RAG 파이프라인 설계해줘
```

### 복합 도메인 작업
```
@bigdata-platform/system-prompts/bigdata-platform-prompts.md
@infra/system-prompts/infra-prompts.md
Spark on K8s 배포 아키텍처 설계해줘
```
