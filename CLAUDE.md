# CLAUDE.md
# ai-prompt-library - BigData Platform

Claude Code 실행 시 이 파일을 자동으로 읽어 프로젝트 컨텍스트를 유지합니다.
아래 참조 파일들을 읽은 후 질문에 답변합니다.

---

## 📂 참조 파일 구조

```
ai-prompt-library/
├── CLAUDE.md                                         ← 현재 파일 (자동 로드)
│
├── bigdata-platform/
│   ├── README.md                                     ← 기술 스택 및 공식 문서 링크
│   └── system-prompts/
│       ├── data-engineer.md                          ← 파이프라인 설계/구현/트러블슈팅
│       ├── data-architect.md                         ← 아키텍처 설계/기술 선정
│       └── data-analyst.md                           ← 쿼리 작성/분석/최적화
│
└── infra/
    ├── README.md
    └── system-prompts/
        ├── devops-engineer.md
        └── ...
```

---

## 📎 자동 참조 파일 목록

Claude Code는 아래 파일들을 컨텍스트로 읽고 작업합니다.

@bigdata-platform/README.md
@bigdata-platform/system-prompts/data-engineer.md
@bigdata-platform/system-prompts/data-architect.md
@bigdata-platform/system-prompts/data-analyst.md

---

## 🤖 행동 기준

### 공통
1. 모든 기술 관련 답변은 공식 문서(Apache, Trino 등 1차 출처)를 기반으로 작성한다.
2. 답변 시 반드시 근거가 된 공식 문서 링크 또는 출처(문서명, 버전, 섹션)를 명시한다.
3. 공식 문서로 확인되지 않은 정보는 추측임을 명확히 표시하고 문서 확인을 안내한다.
4. 기술명 및 API 사용 시 버전을 반드시 명시한다.
5. Deprecated된 방법은 먼저 경고 후 최신 방법으로 안내한다.

### 트러블슈팅
오류 관련 질문 시 반드시 아래 형식으로 답변한다.

```
[오류 원인]   공식 문서 / Known Issue / 릴리즈 노트 기반 원인 분석
[즉시 조치]   당장 적용 가능한 명령어 / 설정 예시
[근본 해결]   변경 전 → 변경 후 설정 예시 포함
[재발 방지]   모니터링 포인트 및 예방 조치
[출처]        공식 문서 링크 / Apache JIRA 링크
```

### 출력 형식
- 일반 답변:     [설명 → 예시 → 출처]
- 아키텍처 답변: [구조 설명 → 기술 비교표 → 트레이드오프 → 출처]
- 쿼리 답변:     [목적 → 쿼리(주석 포함) → 성능 고려사항 → 출처]
- 트러블슈팅:    [오류 원인 → 즉시 조치 → 근본 해결 → 재발 방지 → 출처]
- 한국어로 답변한다.

---

## 🔗 공식 문서 레퍼런스

```
Apache Hadoop    https://hadoop.apache.org/docs/stable
Apache Hive      https://hive.apache.org/docs/latest
Apache Spark     https://spark.apache.org/docs/latest
Apache Kafka     https://kafka.apache.org/documentation
Apache Flink     https://nightlies.apache.org/flink/flink-docs-stable
Apache HBase     https://hbase.apache.org/book.html
Apache Tez       https://tez.apache.org/user_guides.html
Trino            https://trino.io/docs/current
Jupyter          https://docs.jupyter.org/en/latest
Apache JIRA      https://issues.apache.org/jira
```

---

## 📌 작업 범위별 참조 파일 가이드

| 작업 유형 | 주요 참조 파일 |
|---|---|
| 파이프라인 설계 / 구현 | data-engineer.md |
| 아키텍처 설계 / 기술 선정 | data-architect.md |
| 쿼리 작성 / 분석 최적화 | data-analyst.md |
| 운영 오류 / 트러블슈팅 | data-engineer.md + data-architect.md |
| 인프라 연계 작업 | data-engineer.md + infra/system-prompts/ |

---

## 💡 Claude Code 사용 팁

### 특정 파일 추가 참조
```
# 특정 작업 시 파일을 직접 참조
@bigdata-platform/templates/pipeline-design.md 참고해서 설계해줘
@bigdata-platform/few-shots/trino-query.md 형식으로 쿼리 작성해줘
```

### 인프라 연계 작업 시
```
# infra 파일도 함께 참조
@infra/system-prompts/devops-engineer.md
@bigdata-platform/templates/spark-on-k8s.md
```