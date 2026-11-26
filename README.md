# Vision AI Inventory System

Vision AI 파운데이션 모델을 이용해 소규모 비품창고의 관찰 재고와 장부 재고를 비교하고, 재고 부족·불일치·재주문점 도달 상태를 관리자에게 알리는 WMS형 재고 실사 시스템입니다.

## 핵심 원칙

- 영상 관찰 결과가 장부 재고를 자동으로 변경하지 않습니다.
- 불일치 발견 → 확인 요청 → 관리자 승인 → 재고 조정 및 사유 기록 순서로 처리합니다.
- 모델 체크포인트, API 토큰, 운영 데이터베이스와 생성 영상은 Git에 저장하지 않습니다.
- SAM 2.1, Grounding DINO 연구 프로젝트와 최종 애플리케이션 코드를 분리해 관리합니다.

## 계획된 구성

```text
app/        Flask API와 재고 업무 로직
vision/     SAM 3, Optical Flow, Grounding DINO 어댑터
database/   SQLite 스키마와 repository
templates/  서버 렌더링 웹 UI
static/     CSS와 JavaScript
tests/      단위·통합 테스트
docs/       기획과 아키텍처 문서
```

## 개발 로드맵

1. 비품·로케이션·장부 재고·재주문점 모델링
2. 카메라 프레임 기반 관찰 수량 집계
3. 장부 재고와 관찰 재고 비교
4. 불일치 및 부족 알림
5. 관리자 승인과 조정 이력 관리
6. Optical Flow 기반 반출·반입 이벤트 보조 감지

## 기반 연구 프로젝트

- SAM 2.1 실시간 분할, Optical Flow 및 Async Hybrid Tracking
- Grounding DINO 1.6 Pro 텍스트 기반 객체 검출

이 저장소에는 위 연구 저장소 전체를 복사하지 않고, 검증된 기능을 명확한 어댑터 경계로 재사용하거나 재작성할 예정입니다.

## 현재 상태

프로젝트 초기 구조와 저장소 안전 규칙을 구성하는 단계입니다. 애플리케이션 기능은 아직 구현하지 않았습니다.

