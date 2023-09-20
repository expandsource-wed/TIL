### Git 저장방식 알아보기
- Git의 저장방식 SNAPSHOT
    - 변경된 파일을 통째로 저장
- 차이점만 저장하는 방식 : delta
- 순서
    1. 변경된 파일을 저장한다. (save)
    2. 스테이지로 올라간다. (git add)
    3. 스테이지의 스냅샷을 찍는다. (git commit)
    4. 원격저장소 업데이트 (git push)

- 깃으로 관리하는 파일의 4가지 상태
    - 추적안된 상태 (untracked) : add를 하지 않은 경우
    - 추적된 상태 (tracked) : 이미 add가 된 경우
        1. 수정 없음 (unmodified) : 변경사항 없으면
        2. 수정 함 (modified) : 변경사항 있으면
        3. 스테이지 됨(staged) : 스테이징 하면

    - 예시
        - 새로운 파일을 만들었을 때
            - untracked(추적안된 상태)
        - add를 통해 스테이징
            - untracked -> staged
            - 추적안됨 -> 스테이징(애딩)
        - commit을 통해 snapshot
            - staged -> unmodified
            - 스테이징 -> 수정없음
        - 한번 add가 된 상태에서 파일 내용이 변경된 경우
            - unmodified -> modified
