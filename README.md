npm run build

빌드 결과물은 dist/ 폴더에 생성됩니다.

웹 서버의 두 가지 역할

1. 정적 파일 제공 (Static File Serving)

React/Vite 프로젝트를 npm run build 하면 HTML, CSS, JavaScript 등의 정적 파일이 dist/ 폴더에 생성됩니다.

웹 서버는 브라우저의 요청을 받아 이러한 파일을 전달합니다. 이번 실습에서는 nginx가 빌드된 프론트엔드 파일을 사용자에게 제공하는 역할을 합니다.

제가 이해한 바로는 브라우저가 직접 프로젝트의 소스 코드를 실행하는 것이 아니라, 빌드된 결과물을 웹 서버가 전달하고 브라우저가 그것을 받아 화면을 보여주는 구조입니다.

2. 리버스 프록시 (Reverse Proxy)

프론트엔드와 API 서버가 서로 다른 주소나 포트를 사용하면 CORS 문제가 발생할 수 있습니다.

nginx의 리버스 프록시를 사용하면 브라우저는 같은 웹 서버에 /api/... 형태로 요청하고, nginx가 내부적으로 그 요청을 API 서버로 전달할 수 있습니다.

제가 이해한 바로는 사용자는 하나의 서버에 요청하는 것처럼 보이지만, 웹 서버가 요청의 종류에 따라 프론트엔드 파일을 제공하거나 API 서버로 요청을 전달하는 역할을 합니다.

Mini API

Mini API는 mini-api/ 폴더에 있습니다.

주요 API:

GET /api/words

GET /api/words/:word

GET /api/health

Week 3에서 확인한 내용

npm run build를 이용한 production build

dist/ 빌드 결과 확인

nginx를 이용한 정적 파일 제공

reverse proxy를 통한 API 요청

CORS가 발생하는 이유 확인

Docker를 이용한 웹 서버 실행