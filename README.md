# 팀 전장갓겜 - 코드 이용 설명서

### 모델 다운로드 링크
- custom_LLM_llama_weight:   
https://drive.google.com/file/d/1RcIFD17chxzuiYq8SsNEd_SZm2MWeUQn/view?usp=drive_link
- custom_LLM_agiin_weight:   
https://drive.google.com/file/d/1VtLxwBZnAXGK9FrSU-e8lLLMlHYStxxw/view?usp=drive_link


---

### 위 링크와 동일한 모델에 대한 허깅페이스 Public 레포지토리
- 모델 weight를 구글 드라이브에서 직접 다운받는 것이 아니라, 팀 전장갓겜의 허깅페이스 레포지토리에서 학습시켜놓은 모델을 다운받고 추론을 할 수 있다. 현재 추론 코드는 이 방식으로 되어있으나, 모델 링크 또한 첨부하였기에 (구글 드라이브로 직접 다운vs허깅페이스 레포로 로드) 중 원하는 방식으로 추론이 가능하다.
  
- custom_LLM_llama_weight:   
https://huggingface.co/Chaeseung/exp021
- custom_LLM_agiin_weight:   
https://huggingface.co/Chaeseung/dobae_agiin
  
- 만약 허깅페이스로 학습시켜놓은 모델을 로드하는 방법을 원하지 않는 경우에는, inference.ipynb에서 'Chaeseung/exp021'는 './custom_LLM_llama_weight'로 바꿔주고, 'Chaeseung/dobae_agiin'는 './custom_LLM_agiin_weight'로 바꿔준 후, 다운 받은 모델을 동일 디렉토리에 위치시키면 된다.

---

### 파일 설명  
- train.ipynb: 학습 코드  
- inference_Private_Score_복원.ipynb: Private Score 복원용 추론 코드(Output: Embedding Vector 형태로 이뤄진 추론 결과)
- train_data_JJGG.csv: 팀 전장갓겜 전처리 학습 데이터  
- train_keyword_DB_JJGG.csv: 팀 전장갓겜 키워드 데이터베이스  
- valid_JJGG.csv: 팀 전장갓겜 검증 데이터
- test.csv
- train.csv: 학습에 train_data_JJGG.csv를 쓰기 때문에 train.csv는 사용하지 않는다.
- sample_submission.csv
---  


### 추론 결과로 나오는 Output 파일★★★★★
- TEST_Output_QnA.csv: test.csv에 대한 내부평가용 Text 파일(내부평가용 코드의 출력과 동일)  
- final_submission.csv: Private Score 복원을 위한 임베딩 벡터 파일  

---

### 디렉토리 구조  

##### 1. 허깅페이스 레포지토리 모델 로드를 통해 추론하는 경우(추천)
- 모델의 학습과 추론을 위해서는 동일한 디렉토리 내에 [train.ipynb, inference.ipynb, train_data_JJGG.csv, train_keyword_DB_JJGG.csv, test.csv, sample_submission.csv, custom_LLM_llama_weight, custom_LLM_agiin_weight]가 존재해야 한다. 

##### 2. 모델을 직접 다운받아서 추론하는 경우
- 구글 드라이브 링크에서 모델을 직접 다운받아 추론한다면, weight zip파일 2개를 압축 해제해야 하며 압축 해제 후 custom_LLM_llama_weight라는 디렉토리와 custom_LLM_agiin_weight라는 디렉토리가 존재해야 한다.  

- 즉, 압축 해제 이후 모델의 학습과 추론을 위해서는 동일한 디렉토리 내에 [train.ipynb, inference.ipynb, train_data_JJGG.csv, train_keyword_DB_JJGG.csv, test.csv, sample_submission.csv, custom_LLM_llama_weight, custom_LLM_agiin_weight]가 존재해야 한다.  

- 그 후, 위에서 언급한대로 inference.ipynb에서 'Chaeseung/exp021'는 './custom_LLM_llama_weight'로 바꿔주고, 'Chaeseung/dobae_agiin'는 './custom_LLM_agiin_weight'로 바꿔주면 된다.  

---

### 학습 결과로 저장되는 Model weight 디렉토리
- custom_LLM_llama_final  
- custom_LLM_agiin_final  

---

### Environment
- OS: Ubuntu 20.04 LTS    
- Pytorch: 2.0.1   
- CUDA: 11.7   
- cuDNN: 8  

--- 

### 라이브러리 버전
- 라이브러리 버전: requirements.txt에 기재  
- 라이브러리 설치 커맨드: pip install -r requirements.txt   
- 필수 라이브러리는 학습, 추론 코드 내에도 !pip install로 기재하였음

---


### 팀원 연락처  
- 코드 검증 시 문제가 발생한다면 연락주시면 감사하겠습니다.
- 김승희: gyg_9325@naver.com, 010-7285-8426
- 채승호: danielc95@naver.com, 010-5180-8253  

