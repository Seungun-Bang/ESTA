# ESTA
작성자: 고려대 정보보호대학원 석사과정 방승언
이메일: ericbang@korea.ac.kr
이 저장소는 논문 실험에 사용된 노트북과 데이터셋 생성 스크립트를 포함합니다.


## 구성

- `notebooks/01_toolbench_mismatch_ratio_study_experiment.ipynb`: 논문 실험에 사용된 메인 노트북입니다.
- `scripts/build_toolbench_mismatch_dataset.py`: 원본 ToolBench/ToolLLM JSON 파일에서 실험용 mismatch 데이터셋을 생성하는 스크립트입니다.
- `rawdata/`: 원본 JSON 파일을 배치하는 폴더입니다. 실제 raw 데이터는 저장소에 포함하지 않습니다.
- `dataset/`: 노트북이 읽는 실험 데이터셋 위치입니다.

## 실험 데이터

실험 데이터는 GitHub Releases를 통해 공개합니다.

Release에서 `toolbench_mismatch_dataset.csv`를 내려받은 뒤 아래 경로에 배치하면 노트북이 상대경로로 읽습니다.

```text
dataset/toolbench_mismatch_dataset.csv
```

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
