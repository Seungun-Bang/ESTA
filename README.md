# ESTA
작성자: ---

이메일: ---

논문명: 임베딩 벡터 차이를 이용한 LLM 에이전트 도구 호출 정합성 검증 기법

이 저장소는 논문 실험에 사용된 노트북과 데이터셋 생성 스크립트를 포함합니다.

## 실행 환경

아래 버전 조합에서 노트북 실행을 확인했습니다.

- Python: `3.14.0`
- CUDA: `12.6` (`torch` 빌드: `2.11.0+cu126`)
- GPU: `NVIDIA GeForce GTX 1650 SUPER`
- GPU를 사용할 수 없는 환경에서는 임베딩 계산이 CPU로 fallback됩니다.

### 주요 패키지

| 패키지 | 버전 |
| --- | --- |
| `pandas` | `3.0.2` |
| `numpy` | `2.4.4` |
| `scikit-learn` | `1.8.0` |
| `matplotlib` | `3.10.8` |
| `lightgbm` | `4.6.0` |
| `sentence-transformers` | `5.3.0` |
| `torch` | `2.11.0+cu126` |
| `xgboost` | `3.2.0` |

## 구성

- `notebooks/01_toolbench_mismatch_ratio_study_experiment.ipynb`: 논문 실험에 사용된 메인 노트북입니다.
- `scripts/build_toolbench_mismatch_dataset.py`: 원본 ToolBench/ToolLLM JSON 파일에서 실험용 mismatch 데이터셋을 생성하는 스크립트입니다.
- `rawdata/`: 원본 JSON 파일을 배치하는 폴더입니다. 실제 raw 데이터는 저장소에 포함하지 않습니다.
- `dataset/`: 노트북이 읽는 실험 데이터셋 위치입니다.

## 실험 데이터

실험 데이터는 GitHub Releases를 통해 공개합니다.


## 데이터셋 재생성

원본 ToolBench/ToolLLM JSON 파일을 `rawdata/`에 넣은 뒤 아래 명령을 실행하면 노트북용 데이터셋이 생성됩니다.

```bash
python scripts/build_toolbench_mismatch_dataset.py
```

기본 출력 경로는 다음과 같습니다.

```text
dataset/toolbench_mismatch_dataset.csv
```

## 노트북 실행

노트북은 저장소 기준 상대경로로 데이터셋을 찾습니다. 실행 결과는 `outputs/runs/` 아래에 저장됩니다.
