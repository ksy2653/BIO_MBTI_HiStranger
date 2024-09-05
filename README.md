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

## 5. 프로젝트 후기


컨벤션을 정하는 것부터 Readme 파일 작성까지 전 과정을 진행하려니 처음 생각보다 많은 에너지를 썼어요. 좋은 의미로 많이 썼다기보다, 제 능력을 십분 발휘하지 못해서 아쉬움이 남는 쪽입니다. 개발한다고 개발만 해서는 안 된다는 것을 몸소 느껴보는 기간이었던 것 같습니다. 이번 기회로 프로젝트를 진행하면서, 제가 잘하는 점과 부족한 점을 확실하게 알고 가는 건 정말 좋습니다. 기술적인 부분에 있어서는 리액트의 컴포넌트화가 주는 장점을 알았습니다. 조금 느린 개발이 되었을지라도 코드 가독성 부분에 있어서 좋았고, 오류가 발생해도 전체가 아닌 오류가 난 컴포넌트와 근접한 컴포넌트만 살펴보면 수정할 수 있는 부분이 너무 편했습니다. 모두 고생 참 많으셨고 리팩토링을 통해 더 나은 프로젝트 완성까지 화이팅입니다.
