# Creator Comment Emotion Classifier

이 프로젝트는 홍익대학교 **기계학습기초** 수업의 팀 프로젝트로, 댓글 기반의 감정 분석 모델을 개발하고 이를 활용해 **소셜 반응 시각화 플랫폼**을 구축하는 것을 목표로 합니다.

## 📌 프로젝트 개요

| 항목 | 설명 |
|------|------|
| **프로젝트명** | Creator Comment Emotion Classifier |
| **팀 목표** | YouTube / 커뮤니티 댓글에서 감정을 분류하고, 이를 기반으로 시각화 플랫폼을 구현 |
| **진행 기간** | 2025년 9월 ~ 12월 (한 학기) |
| **사용 기술** | PyTorch, Transformers, HuggingFace Datasets, Python, BERT |

## 📚 진행 내용

### 1. 데이터 수집 및 전처리
- `HuggingFace`에서 제공하는 [`dair-ai/emotion`](https://huggingface.co/datasets/dair-ai/emotion) 데이터셋 사용
- 총 **6가지 감정(label)**으로 구성
  - `sadness`, `joy`, `love`, `anger`, `fear`, `surprise`
- 사전학습(pretraining)용으로:
  - 약 7,000건, 11,000건 규모로 커스텀 전처리 수행

### 2. BERT 모델 직접 구현
- Transformer 기반의 **미니 BERT** 모델을 직접 구성
- Masked Language Modeling (MLM)과 Next Sentence Prediction (NSP)을 활용한 사전학습
- 학습 도중 발생 가능한 `NaN`, 마스킹 오류 등 디버깅도 경험

### 3. Fine-tuning 및 감정 분류
- 사전학습된 BERT를 기반으로 감정 분류를 위한 파인튜닝 수행
- 감정 분류기(Classifier Head) 추가
- 최종 모델은 댓글을 입력받아 **6가지 감정 중 하나로 분류**

## 🎯 기말 목표

> **실제 사용자 댓글을 기반으로 소셜 반응을 시각화하는 웹 플랫폼**을 구현할 예정입니다.

- 댓글 입력 → 감정 예측 → 통계/그래프 시각화
- 인플루언서/크리에이터가 팬 반응을 쉽게 파악할 수 있도록 지원

## 🛠️ 사용 환경

- Python ≥ 3.9  
- PyTorch ≥ 2.0  
- Transformers (HuggingFace)  
- tqdm, numpy, pandas 등

---

## 🔗 참고 자료

- HuggingFace Datasets: https://huggingface.co/datasets/dair-ai/emotion  
- BERT 논문: [BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/abs/1810.04805)

> 기계학습기초 수업 (2025 가을학기)의 프로젝트 결과물입니다.
