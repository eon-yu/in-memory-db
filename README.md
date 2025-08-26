# Custom In Memory DB

🧩 목적:
DB 설치가 불가능한 환경에서 SQLite3보다 빠른 커스텀 DB를 직접 구성하여 로그형 데이터를 저장/조회하는 것이 목표.
🧱 요구사항 요약
1. 성능 최우선
SQLite3보다 삽입 및 조회 성능이 뛰어나야 함.
특히 대량의 로그성 데이터에 적합해야 함.
2. DB-like 기능
Table, View, Query 개념 제공
SQL-like 문법 일부 허용 또는 유사 인터페이스
3. 안정성
Volume 마이그레이션 시 동일한 데이터 복원이 가능해야 함.
🛠️ 기본 설계 개념
Rust로 구현
RDBMS는 아님 → 내부적으로는 메모리 기반 또는 단순한 디스크 기반 구조
파일 기반 저장 (volume 간 이동 가능하게)
Index, Compression, Memory Mapping 가능성 고려
