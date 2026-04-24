# SKN26-3rd-4Team

---

# 💬 감정 기반 연인 갈등 완화 대화 추천 시스템

---

## 📌 목차

0. How to Run
1. Team
2. 프로젝트 개요
3. 시스템 아키텍처
4. 데이터 전처리
5. RAG 기반 시스템
6. 테스트 및 평가
7. Streamlit UI
8. 프로젝트 구조
9. 주요 차별점
10. 한계 및 개선 방향
11. 동료 회고

---

## 0. How to Run

<pre>
# 1. 환경 설정
conda env create -f environment.yml
conda activate <env_name>

# 2. 환경 변수 설정
cp .env.example .env
# OPENAI_API_KEY / GEMINI_API_KEY 입력

# 3. 실행
streamlit run app/streamlit_app.py
</pre>

🔗 (https://andysdatabox-7tb38xujsfiq3uaiwdr9na.streamlit.app/)

---

## 1. Team

## 🎁 Andy's Data Box

<table align="center">
  <tr>
    <td align="center" width="125">
      <img src="app/figures/렉스.jpg" width="80"><br>
      <b>김용욱</b><br>
      <a href="https://github.com/yonguk12077-beep">@yonguk12077-beep</a>
    </td>
    <td align="center" width="125">
      <img src="app/figures/우디.jpg" width="80"><br>
      <b>박소윤</b><br>
      <a href="https://github.com/parksoyun9084-cloud">@parksoyun9084-cloud</a>
    </td>
    <td align="center" width="125">
      <img src="app/figures/미스터샤크.jpg" width="80"><br>
      <b>윤찬호</b><br>
      <a href="https://github.com/ch3477-sudo">@ch3477-sudo</a>
    </td>
    <td align="center" width="125">
      <img src="app/figures/저그 황제.jpg" width="80"><br>
      <b>전승권</b><br>
      <a href="https://github.com/eaent">@eaent</a>
    </td>
  </tr>
</table>

## 역할 분담

| 이름 | 역할 |
|------|------|
| 김용욱 | Vector DB 구축 / 프롬프트 설계 / RAG 파이프라인 구성 / 답변 추천 구조 기본 구성 |
| 박소윤 | 서비스 기획·아키텍처 설계 / RAG·감정·위험도 통합 AI 로직 설계 / Streamlit 구현 및 기능 연동 / 데이터 구조 및 문서화 설계 / 일정·마일스톤 관리|
| 윤찬호 | 데이터 전처리 / RAG 검색 구조 비교 / Retrieval 성능 평가 / 답변 추천 흐름 개선 |
| 전승권 | 환경설정 / API / 앱 구조 |

---

---

## 2. 프로젝트 개요

연인 간 대화에서 발생하는 갈등 상황을 분석하고  
감정 및 갈등 위험도를 기반으로 실제 사용할 수 있는 답장 메시지를 추천하는 AI 시스템이다.

### 2-1. 목표

- 감정 기반 상황 이해
- 갈등 위험도 판단
- RAG 기반 유사 사례 활용
- 실사용 가능한 답장 생성

---

## 3. 시스템 아키텍처

<pre>
사용자 입력
→ Streamlit UI
→ 감정 분석 (Gemini)
→ 위험도 분석 (Gemini)
→ RAG 검색 (BM25 + Dense + RRF)
→ 답변 생성 (GPT)
→ 출력 파싱 및 보정
→ UI 출력
</pre>

### 3-1. 핵심 특징

- LLM + RAG 혼합 구조
- 감정 + 위험도 기반 분석
- 실제 메시지 생성 중심 설계
- 출력 안정화 (repair prompt)

---

## 4. 데이터 전처리

### 4-1. 사용 데이터

- 공감형 대화 데이터셋
- 연인 관계 데이터 필터링

### 4-2. 전처리 결과

| 파일 | 역할 |
|------|------|
| continuous_dialogue_dialogue.csv | 대화 단위 감정 흐름 |
| continuous_dialogue_utterance.csv | 발화 단위 감정 |
| rag_documents.csv | RAG 검색 문서 |
| response_pairs.csv | 답변 추천 데이터 |

---

## 5. RAG 기반 시스템

### 5-1. 구조

- BM25 (키워드 검색)
- Dense (임베딩 기반 검색)
- RRF 결합

### 5-2. 효과

- 환각 감소
- 실제 사례 기반 답변 생성
- 상황 적합도 향상

---

## 6. 테스트 및 평가

- 감정 분석 정상 동작
- 위험도 분류 단계별 구분 성공
- 답변 생성 실사용 가능 수준 확보

👉 상세 내용: docs/04_test/

---

## 7. Streamlit UI

- 채팅 인터페이스
- 감정 / 위험도 카드
- 추천 답변 출력

---

## 8. 프로젝트 구조

<pre>
project/
│
├─ data/
├─ src/
│   ├─ emotion/
│   ├─ rag/
│   └─ app_service.py
│
├─ app/
│   └─ streamlit_app.py
│
├─ docs/
├─ tests/
└─ README.md
</pre>

---

## 9. 주요 차별점

- 단순 챗봇이 아닌 답장 생성 시스템
- 감정 + 위험도 기반 대응 전략
- RAG 기반 상황 이해
- 실제 메시지 스타일 출력

---

## 10. 한계 및 개선 방향

- 데이터 다양성 부족
- 감정 분석 정확도 개선 필요
- 실시간 대화 기능 확장 가능

---

## 11. 동료 회고

<table style="width: 100%; border-collapse: collapse; border: 1px solid #ddd; margin-bottom: 30px;">
    <thead>
        <tr style="background-color: #f8f9fa;">
            <th style="width: 15%; border: 1px solid #ddd; padding: 10px;">작성자</th>
            <th style="width: 15%; border: 1px solid #ddd; padding: 10px;">대상자</th>
            <th style="border: 1px solid #ddd; padding: 10px;">회고 내용</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="4" style="text-align: center; font-weight: bold; border: 1px solid #ddd;">김용욱</td>
            <td style="text-align: center; border: 1px solid #ddd;">박소윤</td>
            <td style="border: 1px solid #ddd; padding: 10px;">프로젝트 내에서 주도적으로 회의를 이끌어나가면서 모두가 좋은 의견을 내어 최고의 방안을 선택해 나갈 수 있게 진행 간 좋은 리더십을 보여주셨으며 리드미 작성 및 스트림릿 초기 구성안에 대해 좋은 의견을 내주셔서 팀원들이 좀 더 빠른 진행을 할 수 있게 큰 도움을 주셨습니다.</td>
        </tr>
        <tr>
            <td style="text-align: center; border: 1px solid #ddd;">윤찬호</td>
            <td style="border: 1px solid #ddd; padding: 10px;">데이터 전처리와 주로 쓰일 후보문들과 대화 구조 정리를 담당해주셨으며, 프로젝트 진행 간 전처리 과정을 완료한 후 RAG 파이프라인을 보다 세분화되게 구성해주며 기존의 파이프라인과 병합하여 좀 더 세분화 된 구조를 보여주셨습니다. 또한 팀원분 중 막히는 부분이 있을 때 쉽게 설명해주며 보다 빠른 이해를 도와주셨습니다</td>
        </tr>
        <tr>
            <td style="text-align: center; border: 1px solid #ddd;">전승권</td>
            <td style="border: 1px solid #ddd; padding: 10px;">프로젝트 간 감정 / 위험도 분석을 맡아주셨으며 분석 간 제일 중요했던 감정선의 기준과 관계 위험도의 기준을 잘 정해주셔서 결과값을 내는 데 있어서 프로젝트 간 추구하던 바를 순조롭게 나타낼 수 있게 큰 도움을 주셨으며 개발 간 팀원들한테 생긴 오류를 주도적으로 찾아보고 해결해주면서 진행 간 오류 해결로 지체되는 시간을 단축시켜주셨습니다.</td>
        </tr>
<table style="width: 100%; border-collapse: collapse; border: 1px solid #ddd; margin-bottom: 30px;">
    <thead>
        <tr style="background-color: #f8f9fa;">
            <th style="width: 15%; border: 1px solid #ddd; padding: 10px;">작성자</th>
            <th style="width: 15%; border: 1px solid #ddd; padding: 10px;">대상자</th>
            <th style="border: 1px solid #ddd; padding: 10px;">회고 내용</th>
        </tr>
    </thead>
        <tr>
            <td rowspan="4" style="text-align: center; font-weight: bold; border: 1px solid #ddd;">박소윤</td>
            <td style="text-align: center; border: 1px solid #ddd;">김용욱</td>
            <td style="border: 1px solid #ddd; padding: 10px;">RAG 파이프라인 구축과 Vector DB 구성, 프롬프트 설계를 담당하여 검색과 답변 생성의 기반 구조를 구현해주었습니다. 특히 RAG 흐름 설계 과정에서 핵심 기능 개발에 기여해주었습니다.</td>
        </tr>
        <tr>
            <td style="text-align: center; border: 1px solid #ddd;">윤찬호</td>
            <td style="border: 1px solid #ddd; padding: 10px;">데이터 전처리와 RAG 검색 구조 비교, Retrieval 성능 평가를 담당하여 데이터 품질 확보와 검색 성능 개선에 기여해주었습니다. 전처리 과정 정리와 데이터 구조 이해에 도움이 되었습니다.</td>
        </tr>
        <tr>
            <td style="text-align: center; border: 1px solid #ddd;">전승권</td>
            <td style="border: 1px solid #ddd; padding: 10px;">환경설정과 API 연동, 앱 구조 정리를 담당하여 프로젝트가 정상적으로 실행될 수 있는 기반을 마련해주었습니다. 개발 환경 구성과 기능 연결 과정에서 안정성 확보에 기여해주었습니다.</td>
        </tr>
<table style="width: 100%; border-collapse: collapse; border: 1px solid #ddd; margin-bottom: 30px;">
    <thead>
        <tr style="background-color: #f8f9fa;">
            <th style="width: 15%; border: 1px solid #ddd; padding: 10px;">작성자</th>
            <th style="width: 15%; border: 1px solid #ddd; padding: 10px;">대상자</th>
            <th style="border: 1px solid #ddd; padding: 10px;">회고 내용</th>
        </tr>
    </thead>
        <tr>
            <td rowspan="4" style="text-align: center; font-weight: bold; border: 1px solid #ddd;">윤찬호</td>
            <td style="text-align: center; border: 1px solid #ddd;">김용욱</td>
            <td style="border: 1px solid #ddd; padding: 10px;"> Vector DB 구축과 프롬프트 설계를 진행해 주시고, RAG 문서 검색 파이프라인 구성에도 기여해 주셔서 프로젝트 완성도 향상에 큰 도움이 되었습니다.</td>
        </tr>
        <tr>
            <td style="text-align: center; border: 1px solid #ddd;">박소윤</td>
            <td style="border: 1px solid #ddd; padding: 10px;">프로젝트 주제 선정과 역할 분배 같은 의견 조율 과정에서 먼저 나서 주셔서, 팀이 방향을 빠르게 정하고 원활하게 출발할 수 있었습니다.</td>
        </tr>
        <tr>
            <td style="text-align: center; border: 1px solid #ddd;">전승권</td>
            <td style="border: 1px solid #ddd; padding: 10px;">갈등 상황에서 감정과 위험도를 분석하는 역할을 맡아, 프로젝트의 핵심 차별점을 잘 살려주셨습니다.</td>
        </tr>
<table style="width: 100%; border-collapse: collapse; border: 1px solid #ddd; margin-bottom: 30px;">
    <thead>
        <tr style="background-color: #f8f9fa;">
            <th style="width: 15%; border: 1px solid #ddd; padding: 10px;">작성자</th>
            <th style="width: 15%; border: 1px solid #ddd; padding: 10px;">대상자</th>
            <th style="border: 1px solid #ddd; padding: 10px;">회고 내용</th>
        </tr>
    </thead>
        <tr>
            <td rowspan="4" style="text-align: center; font-weight: bold; border: 1px solid #ddd;">전승권</td>
            <td style="text-align: center; border: 1px solid #ddd;">김용욱</td>
            <td style="border: 1px solid #ddd; padding: 10px;">RAG 파트중 벡터DB 로컬에 생성을 깔끔하게 해주었다</td>
        </tr>
        <tr>
            <td style="text-align: center; border: 1px solid #ddd;">박소윤</td>
            <td style="border: 1px solid #ddd; padding: 10px;">프로젝트 전반 의견표명이 확실,팀 역할 분배를 확실하게 함으로서 주도를 해주셔서 다행이였음</td>
        </tr>
        <tr>
            <td style="text-align: center; border: 1px solid #ddd;">윤찬호</td>
            <td style="border: 1px solid #ddd; padding: 10px;">전처리 데이터셋을 담당 함으로서 자료 준비수월하게 되어서 프로젝트 수행시 나쁘지않았다</td>
        </tr>
       
</table>