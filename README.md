# Uni-D 배터리 열폭주 6단계 분류 — 제출 버전 (v16)

## 팀 정보
- 팀명: Uni-Dthon 8 Team
- 최종 선택 제출 파일: submission_v16.csv

## 개발 환경
- OS: Ubuntu 22.04 LTS
- Python: 3.10
- GPU: NVIDIA GeForce RTX 5080
- 라이브러리: `requirements.txt` 참고

## 파일 구성
| 파일 | 역할 |
|---|---|
| `model.py` | 피처 생성(이미지 통계·센서·과거 방향 시계열)과 앙상블 모델 정의 |
| `train.py` | Train으로 학습, Validation으로 평가, 가중치 저장 |
| `test.py` | 입력 CSV에 들어 있는 행만으로 추론하고 제출 파일 생성 |
| `weights/model_v16.joblib` | 학습된 가중치 모델 |

## 실행 방법
```bash
pip install -r requirements.txt

# 추론 실행 테스트
python test.py --input ./data/battery_data_light/test/test.csv \
               --image_root ./data/battery_data_light/test \
               --model ./weights/model_v16.joblib \
               --output ./submission.csv \
               --sample_submission ./data/battery_data_light/sample_submission.csv
