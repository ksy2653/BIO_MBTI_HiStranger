# 🎥 BIO MBTI 측정 프로젝트

![Nextrise](https://github.com/ksy2653/BIO_MBTI_HiStranger/raw/main/nextrise%20logo.png)

<br>

## 프로젝트 소개

- 본 프로젝트는 2024년 6월 13,14일에 개최된 아시아 최대 규모의 글로벌 스타트업 페어 NextRise 행사 때 진행한 프로젝트입니다.
- NextRise 프로젝트에 시연할 BIO MBTI 측정 시스템 개발 프로젝트
- SOSO device와 IR Camera를 이용해 측정한 bio data와 관객들의 사전 설문 조사를 통해 생체 신호가 알려주는 진짜 BIO MBTI를 관객들에게 제공을 목표

<br>

## 프로젝트 기간 및 인원
프로젝트 기간: 5월 20일 ~ 6월 14일 (working day: 16 days)  
프로젝트 인원: 총 5명

- OOO: 연구 및 개발(mbti 측정 데이터 관련 연구 및 대시보드 개발)
- OOO: 앱, 서버 개발(soso and camera attached flutter app, mongoDB and server)
- OOO: 대시보드 내 비디오 페이지 관련 개발
- OOO: 연구 및 개발(mbti 측정 데이터 관련 연구)
- OOO: api 및 서버 개발(django server and api)

</div>

<br>

## 1. 개발 환경

- Front : Flutter, HTML
- Back-end : Django, MongoDB
- 협업 툴 : Slack, Notion, Github
- 디바이스 : SoSo Device(심박수 등의 생체신호 수집), IR Camera(관객의 표정 변화 촬영)

<br>

## 2. System Flow
1. 관객은 영화를 보는 관점을 조사하는 사전 설문조사를 실시합니다.
2. 관객은 SoSo Device를 착용하고 카메라 앞에서 영화를 시청
3. 영화를 시청하는 동안 관객의 생체 신호와 얼굴 표정 변화 정보 수집
4. 영화가 끝나면 영상이 API를 이용해 서버로 전송
5. 하이스트레인저의 연구 결과를 이용해 영상을 분석하여 사용자의 BIO MBTI 결과값을 제공  
<br>

## 3. 기여한 부분
> MP4 Transfer API 개발
>
> - 시간 단축을 위해 chunk화 시킨 mp4 file을 multi-thread 방식을 이용해 post/get 요청
> 
<br>

> Movie start time, camera start time Transfer API 개발
>
> - MBTI 분석을 위한 영화 시작 시간과 카메라 시작 시간을 받기위해 post 요청을 하고
>   이를 이용해 json 파일을 생성하여 ML 서버로 전송 
> 
<br>

> Post Map 작성 및 시스템 아키텍쳐 작성
>
> - Front와 Back이 주고 받을 값과 순서를 나타내는 Map 작성
> - 시스템 아키텍쳐 및 시스템 플로우 차트 작성
> 
<br>

### 작업 관리

- 매일 아침 MeetUp을 통해 서로의 진행 상황과 블로커를 공유하였습니다.
- Slack과 Notion을 이용해 커뮤니케이션 및 결과 공유를 하였습니다.

<br>

### 시스템 아키텍처 및 코드
- 회사 보안 규정상 공개할 수 없음에 양해부탁드립니다.
  
## 4. 어려웠던 점
> mp4 transfer out of memory issue
>
> - challenge
>   - 10mb mp4 파일 통신은 가능했지만 1gb mp4 파일에서 out of memory error
> - solution 
>   - mp4 파일을 chunk화 시켜서 플러터 앱에서 서버로 전송
<br>

> mp4 transfer 속도 문제
>
> - challenge
>   - 3min 내에 영상을 저장해야 하는 상황 속 시간이 너무 오래 걸리는 문제
> - solution 
>   - multi-threads 방법으로 chunk들을 서버로 보냄 → 시간이 약 2배 단축
<br>

> POST, GET 통신에 대한 이해 부족
>
> - challenge
>   - Django Server 개발 초기에 서버에서 먼저 태블릿들(flutter app)로 post 요청을 보낸다는 것이 기존에 알고 있던 상식과 상충하여 납득이 잘 가지 않음
> - solution 
>   - 팀원들과 post, get 통신에 대해서 많은 의견을 공유하고 배움
>   - 우리 시스템에서는 장고 서버가 클라이언트의 역할을 하고, 태블릿(플러터 앱)이 서버의 역할을 하고 있었던 것으로 django -> flutter로의 post요청이 가능
<br>

## 5. 프로젝트 후기
>  - 이번 프로젝트를 진행하면서 개인적으로는 많이 배울 수 있는 시간이었던 것 같다. 학부 시절에 개념으로만 배웠던 stack 구조, multi-thread 구조 등이 실제 현업에서 어떻게 사용되는지도 배울 수 있었고 기본이라고 생각하며 사용했던 Http get, post 통신에 대해서도 다시 한번 공부할 수 있었다.  
>    
>  - 이번 프로젝트를 진행하면서 디버깅과 예외처리에 대한 중요성을 크게 느꼈다. 정말 다양한 에러 로그를 마주하게 되었는데 단순히 구글링과 챗gpt에 질문하면서 코드를 계속 수정하는 식의 개발이 얼마나 비효율적인지 깨달았다. 코드에 로그를 추가해서 어디서 에러가 나는지 정확하게 파악하고 어떤 문제 때문에 발생하는지를 알아야 개발이 효율적으로 진행이 된다는 점을 다시한번 깨닫게 되었다.
>      
>  - 개발을 한다고 해서 바로 IDE를 켜서 코드를 작성하는게 아니라는 점을 배웠다. 큰 그림을 그려놓고 이에 맞게 코드를 짜는게 더 빠르고 정확한 개발이라는 점을 깨닫게 되었다.
