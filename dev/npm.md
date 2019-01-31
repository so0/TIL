
# NPM 
- NPM (Node Package Manager)
    - 패키지 관리 도구.
        - 패키지
            - 프로젝트에서 사용할 모듈 또는 라이브러리 or 완전한 애플리케이션 or 코드 샘플 등..
    - 노드 설치 시 같이 설치된다.
    - 버전 확인
        - `npm -v` , node -v
    - npm 으로 패키지 설치 시 전역으로(globally) 또는 로컬(locally)로 설치할 수 있다. 
        - 로컬 패키지
            - 각 프로젝트에 종속되는 패키지
        - 글로벌 패키지
            - 보통 개발과정에서 사용, 터미널에서 실행하는 도구들

- 사용법
    - `npm init`
        - `package.json` 추가됨 (직접 만들 필요 없음)
        - npm은 packge.json 파일을 통해 의존성을 관리한다.

        - 의존성
            1. 일반 의존성
            2. 개발 의존성
                - 앱 실행 시 필요없지만 프로젝트 개발 시 필요한 패키지

    - ` npm install 패키지명` (= npm i )
        - 패키지 설치 명령어
        - 프로젝트 루트에서 실행한다.
        - 프로젝트 루트에 `node_modules` 디렉토리가 생긴다.
        - `node_modules` 하위에 로컬 모듈이 설치된다.
        - 로컬 패키지 설치 시 `--save` 또는 `--save-dev` 플래그를 사용한다.
        - 플래그 미사용 시 packge.json 파일에는 등록되지 않음

    - `npm install`
        - node_module 삭제 후, npm install 시 npm이 `package.json`을 읽고 필요한 패키지를 자동으로 설치한다.
        - node_module은 git ignore 하기

