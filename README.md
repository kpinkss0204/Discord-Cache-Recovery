# 💬 Advanced Discord Cache Chat Extractor

PC에 설치된 디스코드(Discord)의 로컬 캐시 바이너리 파일을 직접 분석하여, Gzip 압축 스트림을 해제하고 **대화 내역을 정밀하게 복원·추출**해 주는 고급 PowerShell 스크립트입니다.

---

## 🚀 주요 기능 (Features)

* **디스코드 안전 종료 및 백업**: 실행 중인 디스코드를 강제 종료한 뒤, 캐시 원본 파일(`Cache_Data`)의 손상을 방지하기 위해 바탕화면에 안전하게 백업합니다.
* **Gzip 바이너리 스트림 복원**: 캐시 파일 내부에서 Gzip 압축 매직 넘버(`\x1f\x8b\x08`)를 탐지하여 압축된 원본 JSON 데이터(대화 내용)를 완벽히 복원합니다.
* **Discord Snowflake ID 타임스탬프 변환**: 메시지 ID의 비트 연산을 통해 정확한 작성 시각(Unix 밀리초 변환)을 계산하여 대화 기록에 타임스탬프를 부여합니다.
* **체계적인 결과물 분류**: 
  * 채널별 대화 파일 (`channel_<ID>.txt`)
  * 전체 통합 대화 기록 (`ALL_messages.txt`)
  * 채널별 기간 및 메시지 개수 요약 (`summary.txt`)

---

## 💻 사용 환경 (Prerequisites)

* **OS**: Windows 10 / 11
* **Shell**: PowerShell 5.1 이상 (또는 PowerShell 7+)
* **대상 앱**: PC용 공식 디스코드 데스크톱 앱

---

## ⚙️ 사용 방법 (How to Use)

1. PowerShell을 **관리자 권한** 또는 일반 권한으로 엽니다.
2. 아래의 전체 스크립트 코드를 복사하여 PowerShell 창에 붙여넣고 실행합니다.
