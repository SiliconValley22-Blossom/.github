# ![PurpleLogo-BOutline](https://user-images.githubusercontent.com/78634177/182301688-36ef5a94-8fff-4c76-a35d-45b685071022.png)

흑백 사진을 단 한 번의 클릭만으로 컬러복원하는 서비스입니다.

Blossom이 여러분들의 추억을 다시 그려드리겠습니다. 🌸

---
## System Architecture
![image](https://user-images.githubusercontent.com/55674648/182015290-475222f1-9a9d-4d0d-916d-2d775421f7b5.png)

---
## Tech Stack

<div align =center> 
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"> 
  <img src="https://img.shields.io/badge/Amazon EC2-FF9900?style=for-the-badge&logo=amazon%20ec2&logoColor=black">
  <img src="https://img.shields.io/badge/Amazon S3-569A31?style=for-the-badge&logo=amazon%20s3&logoColor=black">
  <img src="https://img.shields.io/badge/Amazon RDS-527FFF?style=for-the-badge&logo=amazon%20rds&logoColor=black">
  <img src="https://img.shields.io/badge/NGINX-009639?style=for-the-badge&logo=nginx&logoColor=black">
  <img src="https://img.shields.io/badge/react-61DAFB?style=for-the-badge&logo=react&logoColor=black">
  <img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black">
  <img src="https://img.shields.io/badge/styled components-DB7093?style=for-the-badge&logo=styledcomponents&logoColor=black">
  <img src="https://img.shields.io/badge/Font Awesome-528DD7?style=for-the-badge&logo=fontawesome&logoColor=white">
  <img src="https://img.shields.io/badge/gunicorn-499848?style=for-the-badge&logo=gunicorn&logoColor=black">
  <img src="https://img.shields.io/badge/flask-000000?style=for-the-badge&logo=flask&logoColor=white">
  <img src="https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/rabbitMQ-FF6600?style=for-the-badge&logo=rabbitmq&logoColor=white">
  <img src="https://img.shields.io/badge/celery-37814A?style=for-the-badge&logo=celery&logoColor=black">
  <img src="https://img.shields.io/badge/redis-DC382D?style=for-the-badge&logo=redis&logoColor=black">
  <img src="https://img.shields.io/badge/mysql-4479A1?style=for-the-badge&logo=mysql&logoColor=white">
  <img src="https://img.shields.io/badge/pytorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white">
  <img src="https://img.shields.io/badge/google colaboratory-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=black">
  <img src="https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=black">
  <img src="https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=Prometheus&logoColor=black">
  <img src="https://img.shields.io/badge/swagger-85EA2D?style=for-the-badge&logo=swagger&logoColor=black">
  <img src="https://img.shields.io/badge/Git-73398D?style=for-the-badge&logo=git&logoColor=white">
</div>
<b>

# Installation
>### Clone Repository
```
git clone --recursive https://github.com/SiliconValley22-Blossom/docker.git
```

>### Set prod.env in the Settings folder

```
FRONTEND_HOST=frontend
FRONTEND_PORT=3333  
BACKAND_HOST=backend
BACKAND_PORT=5000
AI_HOST=colorization-ai
AI_PORT=5555
RDS_ENDPOINT=
RDS_PORT=3306
RDS_DATABASE=blossom 
RDS_NAME=
RDS_PASSWORD=

S3_BUCKET_NAME=
S3_ID=
S3_SECRET_KEY=
S3_PUBLIC_ACCESS_URL=

RABBITMQ_HOST=rabbit
RABBITMQ_PORT=5672
RABBITMQ_USER=
RABBITMQ_PASSWORD=

JWT_KEY=

MAIL_PASSWORD=
MAIL_SERVER=smtp.gmail.com
MAIL_PORT=465
MAIL_USERNAME=
```

>### Run deployment env. 
```
docker-compose -f docker-compose.prod.yml --env-file settings/prod.env up --build
```

---
## Submodule Directories

<details>
<summary>FRONTEND </summary>

컴포넌트 재사용성을 향상시키기 위하여 아토믹 디자인을 기준으로 디렉토리를 구조화하였습니다.

<img src="https://fe-developers.kakaoent.com/static/34afd4d0a47ff85c8f34295c18c2e374/f058b/atomic-design-flow.png"/>

```
frontend
├── Dockerfile
├── README.md 
├── package.json 
├──src
    ├── App.css
    ├── App.js
    ├── components
    │   ├── atom
    │   │   ├── Button.jsx
    │   │   ├── Display.jsx
    │   │   ├── DownloadButton.jsx
    │   │   ├── Input.jsx
    │   │   ├── Loading.jsx
    │   │   ├── MenuItems_colorize.jsx
    │   │   ├── MenuItems_mypage.jsx
    │   │   ├── MenuList.jsx
    │   │   └── TextLink.jsx
    │   ├── molecule
    │   │   ├── DropDown
    │   │   │   ├── DropDown.css
    │   │   │   ├── DropDown_colorize.jsx
    │   │   │   └── DropDown_mypage.jsx
    │   │   ├── NavBar
    │   │   │   ├── NavBar_colorize.css
    │   │   │   ├── NavBar_colorize.jsx
    │   │   │   ├── NavBar_mypage.css
    │   │   │   └── NavBar_mypage.jsx
    │   │   └── User_info.jsx
    │   ├── organisms
    │   │   ├── AdminWrapper.jsx
    │   │   ├── ChangeInfoWrapper.jsx
    │   │   ├── ColorizeFinishWrapper.jsx
    │   │   ├── ColorizeWrapper.jsx
    │   │   ├── FindPWWrapper.jsx
    │   │   ├── HomeWrapper.jsx
    │   │   ├── LoginWrapper.jsx
    │   │   ├── MyPageWrapper.jsx
    │   │   ├── MyProfileWrapper.jsx
    │   │   ├── OthersUserWrapper.jsx
    │   │   └── SignUpWrapper.jsx
    │   └── page
    │       ├── Admin.jsx
    │       ├── ChangeInfo.jsx
    │       ├── Colorize.jsx
    │       ├── ColorizeFinish.jsx
    │       ├── FindPW.jsx
    │       ├── Home.jsx
    │       ├── Login.jsx
    │       ├── MyPage.jsx
    │       ├── MyProfile.jsx
    │       ├── OthersUser.jsx
    │       └── SignUp.jsx
    ├── fonts
    │   ├── Cormorant-Bold.ttf
    │   ├── Cormorant-BoldItalic.ttf
    │   ├── Cormorant-Italic.ttf
    │   ├── Cormorant-Light.ttf
    │   ├── Cormorant-LightItalic.ttf
    │   ├── Cormorant-Medium.ttf
    │   ├── Cormorant-MediumItalic.ttf
    │   ├── Cormorant-Regular.ttf
    │   ├── Cormorant-SemiBold.ttf
    │   ├── Cormorant-SemiBoldItalic.ttf
    │   └── font.css
    ├── index.css
    ├── index.js
    ├── logo-4.svg
    ├── logo-5.svg
    ├── reportWebVitals.js
    └── setupTests.js
```
</details>

<details>
<summary>BACKAND</summary>

MVC Pattern을 적용하여  Model과 Controller를 Backend에서 관리하도록 하였습니다.

또한 Business Logic과 Service Logic을 분리하였습니다.
<img src="https://velog.velcdn.com/images/y-jin112/post/25995f06-ccfa-497b-8d57-9383c71e1549/image.png"/>
<img src="https://hsalem.com/posts/architecture-styles-layered-architecture/layered-architecture-db-separation.png"/>


```
backend
├── Dockerfile
├── README.md
├── myapp
│   ├── __init__.py
│   ├── configs
│   │   ├── AiServerConfig.py
│   │   ├── DatabaseConfig.py
│   │   ├── JwtConfig.py
│   │   ├── S3Config.py
│   │   ├── __init__.py
│   ├── controller
│   │   ├── AdminController.py
│   │   ├── ApiRouter.py
│   │   ├── LoginController.py
│   │   ├── LogoutController.py
│   │   ├── PhotoController.py
│   │   ├── RefreshController.py
│   │   ├── UserController.py
│   │   ├── __init__.py
│   ├── entity
│   │   ├── Entity.py
│   │   ├── __init__.py
│   ├── service
│   │   ├── AdminService.py
│   │   ├── LoginService.py
│   │   ├── PhotoService.py
│   │   ├── TokenService.py
│   │   ├── UserService.py
│   │   ├── __init__.py
│   ├── util
│   │   ├── EncryptManager.py
│   │   ├── __init__.py
│   └── wsgi.py
└── requirements.txt
```
</details>

<details>
<summary>COLORIZATION-AI</summary>

```
colorization-AI
├── Dockerfile
├── README.md
├── app.py
├── requirements.txt
├── service
│   ├── __init__.py
│   ├── baseColor.py
│   └── generator.py
└── util
    ├── __init__.py
    └── imageLoader.py
```
</details>

---

## System description

![image](https://user-images.githubusercontent.com/55674648/183083098-c507d4ed-72f3-4f44-8b39-135f0f56d467.png)


- 웹서버로 Nginx 사용, 리버스 프록시 구현
- wsgi 미들웨어로 gunicorn 사용 : 안정적인 서비스 제공

![image](https://user-images.githubusercontent.com/55674648/183084822-a4602299-52b0-4be3-8e4a-65766157e26d.png)


- 로그인 시 jwt 토큰을 발급하여 클라이언트 쿠키에 저장시켜 인증/인가에 사용
- refresh 토큰을 관리하기 위해 redis를 사용

![image](https://user-images.githubusercontent.com/55674648/183084862-68d622b3-6e11-486e-9e81-146febf2bf04.png)

- 저희는 동시 요청에 대응하기 위해 task를 메세지큐(rabbitMQ)에 할당하여 관리하도록 설계
- 해당 메시지를 celery에 요청


---

## Features
- 회원가입
<img src="https://user-images.githubusercontent.com/77226122/182764728-c098501b-04e9-4695-8b24-eb797e8e5f24.gif">
  로그인 창에서 버튼을 누르면 Redirect하셔서 볼 수 있습니다.
- 로그인
<img src="https://user-images.githubusercontent.com/77226122/182764835-a1f3e702-01db-4e95-a8bc-ea87e43c0b72.gif">
  회원가입 또는 비밀번호를 찾을 수 있는 링크를 설정해두었습니다.
- 로그아웃
<img src="https://user-images.githubusercontent.com/77226122/182766454-50a3474a-45db-4900-8da2-379948aee233.gif">
  로그아웃을 누르면 홈화면으로 넘어가게됩니다.
  
- 이미지 컬러 복원
<img src="https://user-images.githubusercontent.com/77226122/182765604-f5854f16-84af-40c3-9544-ace192295d52.gif">
  흰색 창 가운데 아이콘을 누르시면 사진을 업로드 할 수 잇으며 "Go Colorize!"버튼을 누르면 잠시 로딩 한 후 컬러사진의 결과를 확인 할 수 있습니다.
- 이미지 다운로드
<img src="https://user-images.githubusercontent.com/77226122/182765939-c1d5d830-f256-47be-a475-214ca1ad21f2.gif">
- 마이페이지
<img src="https://user-images.githubusercontent.com/77226122/182766238-7d8bc8cf-3a69-4d51-87a3-9ecc59b6e7fa.gif">
  이전에 컬러화 시켰던 모든 사진들을 확인 할 수 있으며, 각각의 사진위를 호버할 때 그 사진의 컬러화 전 흑백상태를 확인 할 수 있습니다.
- 마이프로필
<img src="https://user-images.githubusercontent.com/77226122/182766619-d5ba9cee-47a2-4075-b142-ad5de0c70245.gif">
  닉네임과 이메일을 확인 할 수 있고, 비밀번호를 변경 할 수 있습니다.
- 비밀번호 변경
<img src="https://user-images.githubusercontent.com/77226122/182766973-05ee87b3-5904-4b24-87b3-b4e2f2175dfa.gif">
  임시비밀번호를 이메일로 전송하여 비밀번호를 변경할 수 있습니다.
- 관리자 페이지
<img src="https://user-images.githubusercontent.com/77226122/182767344-b0c8f641-a4df-4025-afcc-f930181d4f90.gif">
  어드민 권한을 따로 관리하여 사용자들의 리스트와 사용자들이 제작한 사진을 확인 할 수 있습니다.
- 유저 이미지 확인
<img src="https://user-images.githubusercontent.com/77226122/182794237-c9700347-fd7a-4b86-8088-3a4e36a9ab2d.gif">
  유저의 닉네임을 누르면 각 유저들의 이미지를 확인 할 수 있습니다. 
- 유저 강제 탈퇴
<img src="https://user-images.githubusercontent.com/77226122/182767783-1533aad8-7a7b-4c91-89a2-260c5ba120b8.gif">
  체크박스를 누르고 delete 버튼을 누르면 사용자를 지울 수 있습니다.
- 반응형 적용
<img src="https://user-images.githubusercontent.com/77226122/182768988-355d4ad8-2da6-4aa5-ba07-ffe3be9fd294.gif">
  모바일 환경에서 볼 수 있도록 화면이 일정 너비 이상 작아질때, 환경에 맞게 변경하여 드롭다운 메뉴를 추가하여 구현하였습니다. 또한 화면이 줄어듬에 따라 사진에 있는 그리드도 바뀌는걸 확인 할 수 있습니다.
  
- Monitoring Tools
  prometheus & grafana
  <img src="https://user-images.githubusercontent.com/55674648/182312846-2d815526-84bf-4674-9c28-d809528c4cf6.png">
- [BACKEND API DOC](https://siliconvalley22-blossom.github.io/blossom.github.io/)
---
## Our Team
<table width="950">
    <thead>
    </thead>
    <tbody>
    <tr>
        <th>사진</th>
         <td width="100" align="center">
            <a href="https://github.com/phjppo0918">
                <img src="https://user-images.githubusercontent.com/13298429/132939286-3aa06019-e474-4f42-b164-1813a925d624.png" width="60" height="60">
            </a>
        </td>
        <td width="100" align="center">
            <a href="https://github.com/SEONMl">
                <img src="https://user-images.githubusercontent.com/55674648/182297878-50251278-10f6-4cfd-9438-38cef6f1bf7b.png" width="60" height="60">
            </a>
        </td>
        <td width="100" align="center">
            <a href="https://github.com/asyooniverse">
                <img src="https://user-images.githubusercontent.com/55674648/182299290-6bd80a63-37f0-48da-ae95-5c0ac73ec1fe.png" width="60" height="60">
            </a>
        </td>
        <td width="100" align="center">
            <a href="https://github.com/yjshin229">
                <img src="https://user-images.githubusercontent.com/55674648/182299415-8eb9d968-324f-4c89-8ef5-94d15c338d24.png" width="60" height="60">
            </a>
        </td>
        <td width="100" align="center">
            <a href="https://github.com/hamin924">
                <img src="https://user-images.githubusercontent.com/55674648/182299720-f57a2c02-f28c-4b4b-bb8c-181dc32f04ab.png" width="60" height="60">
            </a>
        </td>
    </tr>
    <tr>
        <th>이름</th>
        <td width="100" align="center">박현준</td>
        <td width="100" align="center">박선미</td>
        <td width="100" align="center">김지윤</td>
        <td width="100" align="center">신영진</td>
        <td width="100" align="center">김하민</td>
    </tr>
    <tr>
        <th>역할</th>
        <td width="150" align="center">
            backend<br>
            devops<br>
            AI<br>
        </td>
        <td width="150" align="center">
            backend<br>
            devops<br>
        </td>
        <td width="150" align="center">
            frontend<br>
            backend<br>
        </td>
        <td width="150" align="center">
            frontend<br>
            AI<br>
        </td>
        <td width="150" align="center">
            frontend<br>
        </td>
    </tr>
    <tr>
        <th>GitHub</th>
        <td width="100" align="center">
            <a href="https://github.com/phjppo0918">
                <img src="http://img.shields.io/badge/phjppo0918-green?style=social&logo=github"/>
            </a>
        </td>
        <td width="100" align="center">
            <a href="https://github.com/SEONMl">
                <img src="http://img.shields.io/badge/SEONMl-green?style=social&logo=github"/>
            </a>
        </td>
        <td width="100" align="center">
            <a href="https://github.com/asyooniverse">
                <img src="http://img.shields.io/badge/asyooniverse-green?style=social&logo=github"/>
            </a>
        </td>
        <td width="100" align="center">
            <a href="https://github.com/yjshin229">
                <img src="http://img.shields.io/badge/yjshin229-green?style=social&logo=github"/>
            </a>
        </td>
        <td width="100" align="center">
            <a href="https://github.com/hamin924">
                <img src="http://img.shields.io/badge/hamin924-green?style=social&logo=github"/>
            </a>
        </td>
    </tr>
    </tbody>
</table>
  
## 지원 브라우저

  
<image src="https://user-images.githubusercontent.com/55674648/183087930-5c4f56d3-8bed-4d8d-86c7-f26c9887332b.png" width="20" height="20"> Chrome|<image src="https://user-images.githubusercontent.com/55674648/183088126-aa986753-ddca-49df-aa1c-d732b374219e.png" width="20" height="20"> Edge|<image src="(https://user-images.githubusercontent.com/55674648/183088660-7fd7aec4-2f0a-4536-9921-878b926169d4.png" width="20" height="20"> FireFox|<image src="https://user-images.githubusercontent.com/55674648/183088361-48d90c6a-3037-4792-ba33-bf6510f2dfd7.png" width="20" height="20"> Safari|
|:---:|:---:|:---:|:---:|
|✔ (84+)|✔ (84+)|✔ (63+)|✔ (14.1+)|  

## Youtube
https://www.youtube.com/watch?v=dkyn-BkEIv0

---
## Reference
---
- [AI 모델](https://github.com/richzhang/colorization)
