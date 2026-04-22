# SKN26-3rd-4Team

---

# 💬 감정 기반 연인 갈등 완화 대화 추천 시스템

---

## 📌 목차
how to run 
url 넣기
1. [Team](#-team)
2. [프로젝트 개요](#프로젝트-개요)
3. [시스템 아키텍처](#시스템-아키텍처)
4. [데이터 전처리 결과](#데이터-전처리-결과)
5. [RAG 기반 시스템 구현](#rag-기반-시스템-구현)
6. [테스트 및 평가](#테스트-및-평가)
7. [Streamlit UI](#streamlit-ui)
8. [프로젝트 구조](#프로젝트-구조)
9. [동료 회고](#동료-회고)

---

## 1.  Team

## 🎁 Andy's Data Box

<table align="center">
  <tr>
    <td align="center" width="125" valign="top">
      <table align="center" width="105">
        <tr>
          <td align="center" height="120">
            <img src=app/figures/렉스.jpg
                 width="80" height="105"
                 style="object-fit:contain;">
          </td>
        </tr>
        <tr>
          <td align="center" height="36"><b>김용욱</b></td>
        </tr>
        <tr>
          <td align="center" height="44">
            <a href="https://github.com/yonguk12077-beep">@yonguk12077-beep</a>
          </td>
        </tr>
      </table>
    </td>
    <td align="center" width="125" valign="top">
      <table align="center" width="105">
        <tr>
          <td align="center" height="120">
            <img src="app/figures/우디.jpg"
                 width="80" height="105"
                 style="object-fit:contain;">
          </td>
        </tr>
        <tr>
          <td align="center" height="36"><b>박소윤</b></td>
        </tr>
        <tr>
          <td align="center" height="44">
            <a href="https://github.com/parksoyun9084-cloud">@parksoyun9084-cloud</a>
          </td>
        </tr>
      </table>
    </td>
    <td align="center" width="125" valign="top">
      <table align="center" width="105">
        <tr>
          <td align="center" height="120">
            <img src="app/figures/미스터샤크.jpg"
                 width="80" height="105"
                 style="object-fit:contain;">
          </td>
        </tr>
        <tr>
          <td align="center" height="36"><b>윤찬호</b></td>
        </tr>
        <tr>
          <td align="center" height="44">
            <a href="https://github.com/ch3477-sudo">@ch3477-sudo</a>
          </td>
        </tr>
      </table>
    </td>
    <td align="center" width="125" valign="top">
      <table align="center" width="105">
        <tr>
          <td align="center" height="120">
            <img src="app/figures/저그 황제.jpg"
                 width="80" height="105"
                 style="object-fit:contain;">
          </td>
        </tr>
        <tr>
          <td align="center" height="36"><b>전승권</b></td>
        </tr>
        <tr>
          <td align="center" height="44">
            <a href="https://github.com/eaent">@eaent</a>
          </td>
        </tr>
      </table>
</table>


| 이름 | 역할                                                     |
|------|--------------------------------------------------------|
| 김용욱 | Vector DB 구축 / 프롬프트 설계 / RAG 파이프라인 구성 / 답변 추천 구조 기본 구성 |
| 박소윤 | 서비스 기획·로직 설계 / Streamlit 대시보드 구현 / 데이터 시각화 / 일정·마일스톤 관리 |
| 윤찬호 | 데이터전처리 / RAG 검색 구조 비교 / Retrieval 성능 평가 / 답변 추천 흐름 개선  |
| 전승권 | 환경설정 / API / 앱 구조                                      |

---

## 2. 프로젝트 개요

연인 간 대화에서 발생하는 갈등 상황을 분석하고,  
감정 및 위험도를 기반으로 적절한 대화 답변을 추천하는 시스템 구축



---

## 3. 시스템 아키텍처

- 입력: 사용자 대화
- 감정 분석
- 위험도 분석
- RAG 기반 유사 사례 검색
- 답변 생성

---

## 4. 데이터 전처리 결과

- 공감형 대화 데이터셋 활용
- 연인 관계 대화 필터링
- 발화 단위 구조화
- CSV / JSON 형태로 변환
- RAG 학습용 문서 생성

---

## 5. RAG 기반 시스템 구현

- Embedding 모델 적용
- Vector DB 구축 (FAISS / 예정: Pinecone)
- Retriever 구성
- Prompt 기반 답변 생성

---

## 6. 테스트 및 평가

- 감정 유사도 평가
- 검색 정확도 분석

---

## 7. Streamlit UI

- 채팅 인터페이스
- 감정 / 위험도 카드
- 추천 답변 출력

---

## 8. 프로젝트 구조

```
project/
│
├─ data/
│   ├─ raw/
│   └─ processed/
│
├─ src/
│   ├─ data/
│   ├─ emotion/
│   ├─ rag/
│   └─ utils/
│
├─ app/
│   └─ streamlit_app.py
│
├─ docs/
│
└─ README.md
```

---

## 9. 동료 회고

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
            <td style="border: 1px solid #ddd; padding: 10px;">RAG 파이프라인 구축과 Vector DB 구성, 프롬프트 설계를 맡아 검색과 답변 생성이 원활하게 이루어질 수 있도록 구현해주었습니다. 프로젝트 핵심 기능 개발과 전체 서비스 흐름 정리에 기여해주었습니다.</td>
        </tr>
        <tr>
            <td style="text-align: center; border: 1px solid #ddd;">윤찬호</td>
            <td style="border: 1px solid #ddd; padding: 10px;">데이터 전처리와 RAG 검색 구조 비교, Retrieval 성능 평가를 맡아 성실하게 수행해주었습니다. 답변 추천 흐름도 함께 개선하며 서비스 완성도 향상에 기여해주었습니다.</td>
        </tr>
        <tr>
            <td style="text-align: center; border: 1px solid #ddd;">전승권</td>
            <td style="border: 1px solid #ddd; padding: 10px;">환경설정과 API 연동, 앱 구조 정리를 맡아 프로젝트가 원활하게 동작할 수 있도록 기여해주었습니다. 개발 환경을 정리하고 기능 연동 과정에서도 적극적으로 참여해 팀 작업에 도움이 되었습니다.</td>
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