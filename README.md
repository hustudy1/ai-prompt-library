# ai-prompt-library

IT 기술 작업 효율화를 위한 AI 프롬프트 라이브러리입니다.
도메인별로 System Prompt, 템플릿, Few-shot 예시, 컨텍스트 문서를 체계적으로 관리합니다.

---

## 📄 루트 파일 설명

| 파일 | 대상 AI 도구 | 역할 | 로드 방식 |
|---|---|---|---|
| `CLAUDE.md` | Claude Code (CLI/IDE) | IT 공통 기초 (한국어) | 프로젝트 폴더 열면 자동 로드 |
| `AGENTS.md` | Cursor, GitHub Copilot 등 | IT 공통 기초 (영문) | AI 도구가 자동 인식 |
| `AGENTS_KR.md` | ChatGPT 등 | IT 공통 기초 (한국어) | 설정에 직접 붙여넣기 |

**공통으로 포함된 내용**
- 공식 문서 우선 원칙, 버전 명시, Deprecated 경고 기준
- 작업 유형별 출력 형식 (일반 / 아키텍처 / 코드 / 트러블슈팅)
- 트러블슈팅 5단계 형식 (오류 원인 → 즉시 조치 → 근본 해결 → 재발 방지 → 출처)
- 도메인별 시스템 프롬프트 참조 가이드 (bigdata / infra / db / ai)

---

## 📁 디렉토리 구조

```
ai-prompt-library/
├── CLAUDE.md                                          # Claude Code 공통 기초 (자동 로드)
├── AGENTS.md                                          # 기타 AI 도구 공통 기초 (영문)
├── AGENTS_KR.md                                       # 기타 AI 도구 공통 기초 (한국어)
├── README.md                                          # 전체 라이브러리 소개 (현재 파일)
│
├── bigdata-platform/                                  # Hadoop 생태계 및 빅데이터 플랫폼
│   ├── system-prompts/
│   │   └── bigdata-platform-prompts.md                # 통합 시스템 프롬프트
│   ├── templates/
│   │   ├── troubleshooting.md                         # 트러블슈팅 요청 템플릿
│   │   ├── pipeline-design.md                         # 파이프라인 설계 요청 템플릿
│   │   └── query-optimization.md                      # 쿼리 최적화 요청 템플릿
│   ├── few-shots/
│   │   ├── troubleshooting-example.md                 # 트러블슈팅 답변 예시
│   │   └── query-example.md                           # 쿼리 최적화 답변 예시
│   └── context-docs/
│       └── cluster-environment.md                     # 클러스터 환경 정보 (선택 입력)
│
├── infra/                                             # 컨테이너 및 오케스트레이션 인프라
│   ├── system-prompts/
│   │   └── infra-prompts.md                           # 통합 시스템 프롬프트
│   ├── templates/
│   │   ├── troubleshooting.md                         # 트러블슈팅 요청 템플릿
│   │   ├── k8s-deployment.md                          # K8s 배포 설계 요청 템플릿
│   │   └── cicd-pipeline.md                           # CI/CD 파이프라인 설계 요청 템플릿
│   ├── few-shots/
│   │   └── troubleshooting-example.md                 # 트러블슈팅 답변 예시
│   └── context-docs/
│       └── infra-environment.md                       # 인프라 환경 정보 (선택 입력)
│
├── db/                                                # 데이터베이스
│   ├── system-prompts/
│   │   └── db-prompts.md                              # 통합 시스템 프롬프트
│   ├── templates/
│   │   ├── troubleshooting.md                         # 트러블슈팅 요청 템플릿
│   │   ├── slow-query.md                              # 슬로우 쿼리 분석 요청 템플릿
│   │   └── schema-design.md                           # 스키마 설계 요청 템플릿
│   ├── few-shots/
│   │   └── slow-query-example.md                      # 슬로우 쿼리 분석 답변 예시
│   └── context-docs/
│       └── db-environment.md                          # DB 환경 정보 (선택 입력)
│
└── ai/                                                # AI/ML 시스템
    ├── system-prompts/
    │   └── ai-prompts.md                              # 통합 시스템 프롬프트
    ├── templates/
    │   ├── troubleshooting.md                         # 트러블슈팅 요청 템플릿
    │   ├── rag-pipeline.md                            # RAG 파이프라인 설계 요청 템플릿
    │   └── prompt-improvement.md                      # 프롬프트 개선 요청 템플릿
    ├── few-shots/
    │   └── rag-pipeline-example.md                    # RAG 파이프라인 설계 답변 예시
    └── context-docs/
        └── ai-environment.md                          # AI 환경 정보 (선택 입력)
```

---

## 📂 카테고리 소개

### 🐘 bigdata-platform
Hadoop 생태계 및 빅데이터 처리 플랫폼과 관련된 프롬프트 모음입니다.

**포함 기술 스택**
- **쿼리 엔진**: Trino, Spark SQL
- **처리 엔진**: Apache Spark, Apache Flink
- **저장소**: HDFS, Apache Hive, Apache HBase
- **메시징**: Apache Kafka
- **분석/탐색**: Jupyter Notebook, Zeppelin
- **메타스토어**: Hive Metastore, Apache Atlas

**주요 활용 시나리오**
- 데이터 파이프라인 설계 및 구현
- 쿼리 튜닝 및 성능 최적화
- 데이터 아키텍처 설계
- 빅데이터 환경 트러블슈팅

---

### 🐳 infra
컨테이너 기반 인프라 구성 및 운영과 관련된 프롬프트 모음입니다.

**포함 기술 스택**
- **컨테이너**: Docker, Docker Compose
- **오케스트레이션**: Kubernetes (K8s), Helm
- **CI/CD**: GitLab CI, GitHub Actions, ArgoCD
- **모니터링**: Prometheus, Grafana, Alertmanager
- **네트워크/스토리지**: Ingress, PV/PVC

**주요 활용 시나리오**
- Docker 이미지 설계 및 최적화
- Kubernetes 클러스터 구성 및 운영
- CI/CD 파이프라인 설계
- 인프라 트러블슈팅 및 장애 대응

---

### 🗄️ db
관계형/비관계형 데이터베이스 설계, 최적화, 운영과 관련된 프롬프트 모음입니다.

**포함 기술 스택**
- **RDBMS**: PostgreSQL, MySQL, MariaDB
- **NoSQL**: Redis, MongoDB, Elasticsearch
- **분산 DB**: Apache Cassandra, TiDB
- **도구**: EXPLAIN ANALYZE, pg_stat_statements, PgBouncer

**주요 활용 시나리오**
- 슬로우 쿼리 분석 및 인덱스 최적화
- 스키마 설계 및 데이터 모델링
- Replication / 백업 / 복구 전략
- DB 트러블슈팅 및 장애 대응

---

### 🤖 ai
LLM 활용 시스템, ML 파이프라인, MLOps와 관련된 프롬프트 모음입니다.

**포함 기술 스택**
- **LLM/API**: Claude (Anthropic), OpenAI GPT, Ollama
- **프레임워크**: LangChain, LlamaIndex, Hugging Face
- **벡터 DB**: Chroma, Pinecone, Weaviate, pgvector
- **서빙**: FastAPI, vLLM, Triton Inference Server
- **MLOps**: MLflow, Kubeflow, Airflow

**주요 활용 시나리오**
- RAG 파이프라인 설계 및 구현
- 프롬프트 엔지니어링 및 최적화
- 모델 서빙 및 MLOps 파이프라인
- LLM 관련 트러블슈팅

---

## 📋 폴더 구성 규칙

각 도메인은 아래 4개의 하위 폴더를 동일한 구조로 유지합니다.

| 폴더 | 역할 | 사용 방법 |
|---|---|---|
| `system-prompts/` | AI 역할 및 행동 기준 정의 | AI 도구 설정에 붙여넣기 또는 `@경로`로 직접 참조 |
| `templates/` | 작업 요청 시 반복 입력을 줄이는 틀 | 항목 채워서 대화 첫 메시지로 전송 |
| `few-shots/` | 원하는 입출력 패턴 예시 | 템플릿과 함께 전송하여 답변 품질 유도 |
| `context-docs/` | 운영 환경, 버전, 컨벤션 등 배경 문서 | 내용 작성 후 대화에 첨부 (비어있으면 생략) |

---

## 🚀 사용 방법

### Step 1. 공통 기초 설정 (최초 1회)

| AI 도구 | 설정 방법 |
|---|---|
| Claude Code | `ai-prompt-library/` 폴더에서 실행 시 `CLAUDE.md` 자동 로드 |
| ChatGPT | Settings > Customize ChatGPT에 `AGENTS_KR.md` 내용 붙여넣기 |
| Cursor / Copilot | `AGENTS.md` 자동 인식 |

### Step 2. 도메인 시스템 프롬프트 참조

작업 도메인에 맞는 시스템 프롬프트를 함께 참조합니다.

```
# Claude Code에서 직접 참조
@bigdata-platform/system-prompts/bigdata-platform-prompts.md 참고해서 Spark OOM 해결해줘
@infra/system-prompts/infra-prompts.md 참고해서 K8s Pod 오류 분석해줘
@db/system-prompts/db-prompts.md 참고해서 슬로우 쿼리 최적화해줘
@ai/system-prompts/ai-prompts.md 참고해서 RAG 파이프라인 설계해줘

# 복합 도메인 작업
@bigdata-platform/system-prompts/bigdata-platform-prompts.md
@infra/system-prompts/infra-prompts.md
Spark on K8s 배포 아키텍처 설계해줘
```

### Step 3. 템플릿 작성

`templates/` 에서 작업에 맞는 템플릿을 선택하고 항목을 채워 대화 첫 메시지로 전송합니다.

```
예: bigdata-platform/templates/troubleshooting.md
→ 오류 메시지, 환경, 시도한 것 채워서 전송
```

### Step 4. Few-shot 예시 첨부 (선택)

`few-shots/` 에서 원하는 출력 형식의 예시를 골라 템플릿과 함께 전송하면 답변 품질이 향상됩니다.

### Step 5. Context 문서 첨부 (선택)

`context-docs/` 에 운영 환경 정보를 채워두면 버전, 클러스터 규모 등을 반복 입력하지 않아도 됩니다.

---

## 🔖 네이밍 컨벤션

```
파일명      : kebab-case 사용          (예: slow-query.md)
폴더명      : kebab-case 사용          (예: system-prompts/)
카테고리명  : 기술 도메인 기준 명명    (예: bigdata-platform/, infra/)
```

---

## 🗺️ 확장 로드맵

```
ai-prompt-library/
├── bigdata-platform/    ✅ 완성
├── infra/               ✅ 완성
├── db/                  ✅ 완성
├── ai/                  ✅ 완성
├── mlops/               🔜 예정
├── security/            🔜 예정
└── backend/             🔜 예정
```

---

## 📌 기여 방법

1. 카테고리 폴더 구조 규칙을 따를 것
2. 각 파일 상단에 목적, 사용 방법, 적용 대상 명시
3. 실제 사용해본 프롬프트만 추가 (검증되지 않은 내용 지양)
4. few-shots 예시는 실제 동작한 Q&A 기반으로 작성
