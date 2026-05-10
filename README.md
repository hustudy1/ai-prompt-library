# ai-prompt-library

AI 작업 효율화를 위한 프롬프트 라이브러리입니다.
도메인별로 System Prompt, 템플릿, Few-shot 예시, 컨텍스트 문서를 체계적으로 관리합니다.

---

## 📁 디렉토리 구조

```
ai-prompt-library/
├── README.md                        # 전체 라이브러리 소개 (현재 파일)
│
├── bigdata-platform/                # Hadoop 생태계 및 빅데이터 플랫폼
│   ├── README.md
│   ├── system-prompts/
│   ├── templates/
│   ├── few-shots/
│   └── context-docs/
│
└── infra/                           # 컨테이너 및 오케스트레이션 인프라
    ├── README.md
    ├── system-prompts/
    ├── templates/
    ├── few-shots/
    └── context-docs/
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
- **오케스트레이션**: Kubernetes (K8s)
- **패키지 관리**: Helm
- **모니터링**: Prometheus, Grafana
- **네트워크/스토리지**: Ingress, PV/PVC

**주요 활용 시나리오**
- Docker 이미지 설계 및 최적화
- Kubernetes 클러스터 구성 및 운영
- 컨테이너 기반 빅데이터 플랫폼 배포
- 인프라 트러블슈팅 및 장애 대응

---

## 📋 폴더 구성 규칙

각 카테고리는 아래 4개의 하위 폴더를 동일한 구조로 유지합니다.

| 폴더 | 역할 | 사용 방법 |
|---|---|---|
| `system-prompts/` | AI 역할 및 행동 기준 정의 | Claude Settings에 붙여넣기 |
| `templates/` | 프로젝트/작업 시작 시 사용하는 틀 | 항목 채워서 대화 첫 메시지로 전송 |
| `few-shots/` | 원하는 입출력 패턴 예시 | 템플릿과 함께 전송하여 답변 유도 |
| `context-docs/` | 기술 스택, 컨벤션 등 배경 문서 | 필요 시 대화에 첨부 |

---

## 🚀 사용 방법

### Step 1. System Prompt 설정
`system-prompts/` 에서 역할에 맞는 파일을 선택해 Claude Settings에 등록합니다.
등록 후 모든 대화에 자동으로 반영됩니다.

### Step 2. 프로젝트 템플릿 작성
`templates/` 에서 작업에 맞는 템플릿을 선택하고 항목을 채워 대화 첫 메시지로 전송합니다.

### Step 3. Few-shot 예시 참고
`few-shots/` 에서 원하는 출력 형식의 예시를 골라 템플릿과 함께 전송합니다.

### Step 4. Context 문서 첨부 (선택)
`context-docs/` 의 배경 문서를 필요 시 대화에 붙여넣어 더 정확한 답변을 유도합니다.

---

## 🔖 네이밍 컨벤션

```
파일명      : kebab-case 사용          (예: data-engineer.md)
폴더명      : kebab-case 사용          (예: system-prompts/)
카테고리명  : 기술 도메인 기준 명명    (예: bigdata-platform/, infra/)
```

---

## 🗺️ 확장 로드맵

현재 구성된 카테고리 외 아래 도메인으로 확장 예정입니다.

```
ai-prompt-library/
├── bigdata-platform/    ✅ 구성 중
├── infra/               ✅ 구성 중
├── mlops/               🔜 예정
├── security/            🔜 예정
└── backend/             🔜 예정
```

---

## 📌 기여 방법

1. 카테고리 폴더 구조 규칙을 따를 것
2. 각 파일 상단에 목적, 사용 방법, 적용 대상 명시
3. 실제 사용해본 프롬프트만 추가 (검증되지 않은 내용 지양)
4. PR 시 어떤 상황에서 효과적이었는지 설명 첨부
