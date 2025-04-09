# LangGraph 기반 대화 라우팅 시스템 (openai api warpping)

이 프로젝트는 LangGraph를 활용하여 사용자의 입력을 분류하고 적절한 대화 모델로 라우팅하는 시스템입니다.

## 주요 기능

- **입력 분류**: 사용자 입력을 감성 대화, 기술 질문, 정보 검색 중 하나로 분류
- **다중 모델 활용**: 각 대화 유형에 최적화된 다른 LLM 모델 사용
- **RAG(Retrieval Augmented Generation)**: 정보 검색 요청에 대해 벡터 데이터베이스 활용
- **FastAPI + LangServe**: FastAPI와 LangServe를 통하 Back-end 서버 구현
- **Streamlit Front-end**: Streamlit을 통해 Front-end 구현
- **Docker Compose**: Docker Compose를 통해 Back-end와 Front-end 서버를 Docker image로 만듦.(아직 미구현)

## 기술 스택

- **LangChain**: LLM 애플리케이션 구성 프레임워크
- **LangGraph**: LLM 상태 머신 구축 프레임워크
- **FastAPI**: API 서버 구현
- **OpenAI API**: 다양한 LLM 모델 활용 (GPT-3.5-turbo, GPT-4)
- **FAISS**: 벡터 데이터베이스
- **Streamlit**: Front-end 서버 구현
- **Docker Compose**: Docker Compose로 Front/Back end 서버를 docker image로 생성

## 시스템 구조

1. **분류기 노드**: 사용자 입력을 분석하여 적절한 대화 유형으로 분류
2. **감성 대화 노드**: 감정적인 대화에 특화된 GPT-4 모델 사용
3. **기술 질문 노드**: 기술적 질문에 특화된 GPT-4 모델 사용
4. **RAG 노드**: 정보 검색 요청에 대해 벡터 데이터베이스 검색 후 응답 생성


## 설치 및 실행

1. 환경 설정:
   ```
   pip install -r requirements.txt
   ```

2. `.env` 파일 생성:
   ```
   OPENAI_API_KEY=your_api_key_here
   ```

3. 서버 실행:
   ```
   python app.py
   ```

4. API 엔드포인트:
   - `/graphbot`: 대화 시스템 API 엔드포인트


## 추가 구현 사항
|구현사항|체크|
|--|--|
|streamlit으로 프론트엔드 구현||
|Docker compose로 image를 만들어서 배포||