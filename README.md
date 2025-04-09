# LangGraph 기반 대화 라우팅 시스템 (openai api warpping)

## 프로젝트 개요
'비서'란 정말 바쁜 CEO 혹은 부를 많이 쌓은 회장님과 어울리는 수식어였습니다.  
하지만 Ai가 보급된 현재,
비록 운전을 대신 해줄 수는 없지만  
매일 아침 날씨 정도는 미리 알려줄 수 있으며 필요한 정보를 대신 수집해 주는 비서가 있다면,  
그리고 그런 비서가 24시간 나와 함께 지낸다면  
시간을 아낄 수 있음은 물론이고 성장력 또한 그를 만나기 전과 확연히 다를 것입니다.  

요약: 이 프로젝트는 LangGraph를 활용하여 사용자의 입력을 분류하고 적절한 대화 모델로 라우팅하는 시스템입니다.


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

2. `.env` 파일 구성:
   ```
   OPENAI_API_KEY=your_api_key_here
   ```

3. 서버 실행:
   ```
   # back-end
   python app.py

   # front-end
   stramlit run front-end.py
   ```

4. API 엔드포인트:
   - `/graphbot`: 대화 시스템 API 엔드포인트


## 추가 구현 사항
|구현사항|체크|
|--|--|
|streamlit으로 프론트엔드 구현|V|
|Docker compose로 image를 만들어서 배포||
|VectorDB 내 문서 추가||
|Conversation Memory 추가||
|Agent System||
|MCP||
|NoSQL을 추가하여 대화 내역 저장||
