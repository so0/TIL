
# Git FLow
- Git FLow란?
    - git 브랜치 관리 전략 중 하나 (그 외 github flow, gitlab flow)
    - Vincent의 branching model은 “feature – **develop** – release – hotfixes – **master**” 단계로 branch를 나눠서 코드를 관리하는 전략이다. 

- Git FLow 장점
    - feature 브랜치를 이용해 기능 개발의 책임 소재를 명확히 할 수 있다.
    - 개발 버전과 제품 버전의 개별 관리가 가능.
    - feature 브랜치와 hotfix 커밋 취합하면 이전 버전과의 변경점을 쉽게 알 수 있다.

- 주요 (핵심) 브랜치
    - develop , master
    - 추가적으로 생성, 삭제가 되지 않는다.
- 보조 (지원) 브랜치
    - feature, release, hotfix
    - 주요 브랜치와 다르게 작업이 끝나면 삭제됨     

- 5단계
    1. Feature
        - 단위 기능을 개발하는 브랜치
        - 기능 개발이 완료될 때 까지 유지
        - 완성 시 develop 브랜치에 병합
        - 가장 많이 생성 , 삭제가 일어남
    2. Develop
        - 개발 중인 제품
        - 현재 개발이 진행중인 메인 브랜치.
        - 다음 릴리즈를 위해 개발중인 최신 버전
    3. Release
        - 배포 버전 관리
        - develop 브랜치 상태가 배포할 수 있는 상태일때 생성하는 브랜치.
        - 각종 오류 사항이나 문제를 검토, 수정하는 일종의 테스트 서버로 볼 수 있음
        - 놓친 버그 수정 후 master에 병합 , develop에도 적용
    4. Hotfix
        - 배포된 제품의 긴급 버그 수정
        - Developt, Feature 브랜치를 거치지 않고 수정하는 단계
        - 수정 사항은 develop, master에 반영될 수 있도록 병합한다.
    5. Master
        - 제품을 실제 서버에 배포
        - 최종 형태의 메인 브랜치
        - 최종 릴리즈에 사용되는 안정된 버전


