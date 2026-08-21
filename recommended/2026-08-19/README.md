# Daily paper recommendations — 2026-08-19

## 검색 정보
- **연구 날짜(research date)**: 2026-08-19
- **실제 검색 창(search window)**: 1일 창(2026-08-19)에서 결과가 없어 7일 창(2026-08-12 ~ 2026-08-19)으로 확대, 관련 논문이 1편뿐이라 30일 창(2026-07-20 ~ 2026-08-19)까지 재확대하여 최종 검색
- **검색 쿼리**: `chest X-ray deep learning multi-institution generalization`

## 코호트 개요 (masked, cohort-level only)
- 총 272건의 검사, 153명의 고유 환자
- 성별: 여 136건(평균 연령 약 54.3세), 남 136건(평균 연령 약 48.7세)
- 촬영 자세: PA 184건, AP 88건
- 5개 기관(INST01–05)에서 수집된 다기관 흉부 X-ray 데이터
- 주요 소견 분포(다중 라벨): No Finding 145건, Infiltration 21건, Atelectasis 16건, Nodule 7건, Fibrosis 6건, Effusion 6건, Cardiomegaly 5건, Pneumothorax 5건 등. Effusion+Infiltration, Atelectasis+Infiltration 등 복합 소견도 다수 관찰됨
- 각 검사에는 판독의(radiologist), 판독문(report_text), 임상 정보(clinical_info)가 자유 텍스트로 함께 저장되어 있음

이 데이터는 다기관에서 수집된 다중 라벨 흉부 X-ray 판독 코호트로, 기관·장비·촬영 조건의 이질성과 판독 보고서 텍스트가 함께 존재하는 것이 특징입니다.

## 비교 축 (axes)
- **기관 간 일반화**: 여러 기관/사이트에서 수집된 데이터에 대한 모델의 전이성과 견고성
- **판독문 연계**: 자유 텍스트 판독 보고서를 학습 신호나 설명 근거로 활용하는 방법
- **다중 소견 분류**: 여러 흉부 소견이 동시에 존재하는 다중 라벨 분류 과제에서의 성능
- **판독 가능성/설명력**: 예측을 임상적으로 해석 가능한 형태로 분해하는 접근

## 선정 논문

### 1. Grounding Radiology Report Findings into Medical Image Segmentation (CF2Seg)
- **venue**: npj Digital Medicine (2026-07-28)
- **link**: https://doi.org/10.1038/s41746-026-03051-0
- **axes**: 기관 간 일반화, 판독문 연계, 다중 소견 분류
- 판독 보고서 소견 문장을 직접 학습 신호로 삼아 흉부 X-ray 병변을 분할하는 CF2Seg는 53,386건의 다기관 벤치마크에서 분포 변화와 주석 부족에도 안정적 성능을 보였습니다.
- 우리 코호트는 5개 기관, 272건 규모로 판독문(report_text)과 다양한 소견(Infiltration, Atelectasis 등)이 함께 저장되어 있어 이 접근과 데이터 구조가 직접 맞물립니다.
- 다만 우리 데이터에는 픽셀 단위 전문가 주석이 없어 논문의 분할 정확도 수치를 직접 검증할 수는 없습니다.

### 2. CLEAR: an auditable foundation model for radiology grounded in clinical concepts
- **venue**: Nature Biomedical Engineering (2026-07-22)
- **link**: https://doi.org/10.1038/s41551-026-01741-4
- **axes**: 기관 간 일반화, 다중 소견 분류, 판독 가능성/설명력
- 예측을 개별 임상 개념 기여도로 분해하는 CLEAR는 미국·유럽·아시아 4개 외부 코호트에서 최고 수준 성능과 감사 가능한 제로샷 탐지를 함께 달성했습니다.
- 우리 코호트는 다중 라벨 소견과 AP/PA 혼합 촬영, 5개 기관 데이터가 공존해 CLEAR가 다루는 다기관·다소견 해석 가능성 검토에 적합합니다.
- 다만 CLEAR 검증에 쓰인 것과 같은 대규모 외부 주석 코호트가 우리에게 없어 절대 성능 수치를 재현할 수는 없습니다.

### 3. QoQ-Med3: a multimodal reasoning foundation model for clinical analysis
- **venue**: npj Digital Medicine (2026-07-25)
- **link**: https://doi.org/10.1038/s41746-026-02945-3
- **axes**: 기관 간 일반화, 다중 소견 분류
- 여러 임상 사이트의 이질적 데이터에 대한 전이성을 평가한 QoQ-Med3는 공개 데이터만으로 학습했음에도 외부 보류 코호트와 사설 병원 데이터셋 모두에 일반화되었습니다.
- 우리 코호트도 5개 기관, 서로 다른 장비와 촬영 조건이 혼재된 다기관 데이터로, 사이트 간 전이성 검증 방식을 참고할 만합니다.
- 다만 이 논문은 흉부 X-ray 특이적 검증 수치를 제공하지 않아 직접적인 성능 비교 근거로 삼기는 어렵습니다.

## 검토 안내
위 추천은 자동화된 검색·필터링 결과이며, 임상 적용 전 반드시 담당 의사의 검토가 필요합니다. 각 논문의 `relevance`, `caveat`, `check` 항목은 우리 코호트 수준 통계에 근거한 참고용 메모이며 환자 단위 정보는 포함하지 않습니다.
