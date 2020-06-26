---
---
# Open Source

시험문제 25문제 시간 30분
(객관식10, 짧은 주관식12~13, 약간 긴 주관식3~4개)

---
1. intro
 - git init: 깃을 사용할 수 있또록 디렉토리를 초기화한다.
 - cat file: 터미널 창에서 간단한 텍스트 문자의 내용을 확인한다.
 - git add file: 수정한 파일을 스테이징 한다.
 - git rm --cached: 스테이징을 취소한다.
 - git commit -m "message": 커밋할 때 그 버전에 어떤 변경사항이 있었는지 메세지를 기록한다.
 - git status: 커밋 한 후 작업 디렉토리의 상태를 나타내 준다.
 - git log: 커밋한 기록을 자세히 볼 수 있다.
 - git commit -am: 스테이징과 커밋을 한꺼번에 할 수 있다.
 - git log --stat: 커밋에 관련된 파일 전부 볼 수 있다.

2. 49p
 - git remote add origin: 원격 저장소에 연결합니다.
 - git remote -v: 원격 저장소에 연결됐는지 확인합니다.
 - git push -u origin master: 지역저장소의 커밋을 맨 처음 원격 저장소로 올립니다.
 - git push: 원격 저장소의 커밋을 지역저장소로 가져옵니다.
 - git pull: 지역저장소의 커밋을 원격 저장소로 올립니다.
 - ssh--keygen: SSH 키를 만듭니다.

3. 88p
 - git config user.name 'easys': 깃 환경에서 이름을 'easys'로 지정합니다.
 - git config user.email 'doit@easys.co.kr': 깃 환경에서 메일을 'doit@easys.co.kr'로 지정합니다.
 - git init: 현재 위치에 지역 저장소를 만듭니다.
 - git status: 깃 상태를 확인합니다.
 - git add ch01.txt: ch01.txt 파일을 스테이지에 올립니다.
 - git commit -m 'ch01': 커밋 메시지 'cho1'를 붙여 커밋합니다.
 - git commit -am 'ch02' or git commit -a -m 'ch02': 메시지 'ch02'를 붙여서 스테이징과 커밋을 동시에 합니다.
 - git log: 커밋 정보를 확인합니다.

4. 103p
 - git branch fixed: 새로운 브랜치 fixed를 만듭니다.
 - git checkout fixed: fixed 브랜치로 체크아웃 합니다.
 - git log --oneline: 커밋로그에서 한 줄에 한 커밋씩 표시합니다.
 - git add .: 수정할 전체 파일을 스테이지에 올립니다.
 - git log --branches --graph: 커밋 로그에 각 브랜치의 커밋을 그래프로 표시합니다.
 - git merge fixed: fixed 브랜치를 master 브랜치에 병합합니다.
 - git cat edit.txt: 터미널 창에서 edit.txt 내용을 확인합니다.
 - git init doit: doit 디렉터리를 만드는 동시에 지역 저장소로 만듭니다.
 - git reset c1 커밋할 캐시: 현재 커밋을 다른 브랜치에 있는 C1 커밋으로 되돌립니다.
 - git branch -d fixed: 병합이 끝난 fixed 브랜치를 삭제합니다.

5. 137p
 - git clone 복사한 주소 myhome: 원격 저장소를 myhome이라는 지역 저장소로 복제합니다.
 - git fetch: 원격 저장소의 커밋을 가져오기만 하고 병합하진 않습니다.
 - git checkout FETCH_HEAD: 패치로 가져온 정보가 있는 브랜치(FETCH_HEAD)로 이동합니다.
 - git merge FETCH_HEAD: 패치로 가져온 정보가 있는 브랜치(FETCH_HEAD)를 master 브랜치로 병합합니다.
 - git config --global user.name "yeong": 현재 깃 환경에서 사용할 이름을 지정합니다.
 - git config --global user.email "exam@email.com": 현재 깃 환경에서 사용할 메일 주소를 지정합니다.
 - git checkout -b fixed: 브랜치를 만드는 것과 동시에 체크아웃 합니다.
 
---
1. 5p-4차산업혁명(바이오, 에너지, 지구공학, 우주기술 등 WEF 클라우드 슈밥이 제시; 다보스 세계경제포럼 회장)

2. 6p-4차산업혁명 9가지 기술
 - 자율주행차: 위험을 인지하고 스스로 목적지까지 운전자의 조작 없이 안전운행
 - 인공지능: 소프트웨어로서 인간의 판단, 언어, 학습, 문제해결 등을 컴퓨터로 하여금 가능하게 함
 - 빅데이터: SNS등 소셜 미디어를 통해 생성되는 엄청난 데이터 양
 - 로봇: 사람과 유사한 모습과 기능을 가진 기계
 - 사물인터넷: 사물들 간의 센서에 의해 연결
 - 블록체인: 온라인 금융정보를 블록으로 연결하여 P2P 네트워크 분산 환경에서 중앙관리가 아닌 네트워크 내의 모든 참여자가 공동으로 정보를 검증
 - 가상현실: 컴퓨터를 이용하여 인공적으로 만든 실제와 유사
 - 드론
 - 핀테크: 조종사가 직접 탐승하지 않고 원격조종
 
3. 8p-인공지능 정의
 - 인공지능이란 인간의 지능이 갖고 있는 기능을 갖춘 컴퓨터 시스템으로, 인간의 기능을 기계 등에 인공적으로 구현하는 것을 말한다. 인공지능의 구현을 위해서는 컴퓨터 시스템, 인공지능 구현 알고리즘 그리고 빅데이터가 필요하며 이러한 빅데이터를 효과적으로 관리 분석하는 핵심 기술로서 미래를 예측하고 보다나은 지능형 시스템을 구현 할 수 있다.

4. 17p-OSS 정의
 - 소스 코드를 공개해 누구나 특별한 제한 없이 그 코드를 보고 사용할 수 있는 오픈소스 라이선스를 만족하는 소프트웨어로서 통상 간략하게 오픈소스라고 말하기도 한다.
 - 소프트웨어의 내용인 소스코드가 공개되어 특정 라이선스 방식을 통해 배포되고, 수정, 복제, 사용, 재배포가 자유로운 소프트웨어를 지칭한다.
 
5. 18p-깃허브: 인공지능 관련 알고리즘, 프로그래밍 언어, 응용분야, 개발 도구 등에 많은 오픈소스가 있으며 다양하게 활용되고 있다.

6. 19p-오픈소프트웨어의 중요성
 - ClOSE  OPEN
 - Close HW/Data/SW Source Code  Open Hw/Data/SW Source Code
 - 폐쇄적 혁신  개방적 혁신
 - 소유, 사유재  공유, 공공재
 - 파이브라인 경제  플랫폼 경재
  
7. 23p-소프트웨어 종류와 구조

![OpenSource_1](https://raw.githubusercontent.com/Paransaik/Paransaik.github.io/master/_images/OpenSource_1.png)

8. 24p-소프트웨어 라이프 사이클과 개발 단계★

![OpenSource_2](https://raw.githubusercontent.com/Paransaik/Paransaik.github.io/master/_images/OpenSource_2.png)

9. 25p-폭포수 모델★
 - 폭포수 모델로 개발된 소프트웨어에 대해 고객의 요구사항은 변할 수밖에 없다.
 - 고객의 유고사항을 반영할 경우 유지 보수 단계에서의 오류수정은 사전 단계의 오류수정 보다 더 많은 비용이 발생한다.
 - 단점을 극복하기 위해 소규모 프로젝트 활동으로 나누어 각 반복 주기 이후 부분적으로 완성되어진 모델이 산출된다.
 
10. 27p-애자일 프로세스★
 - 처음부터 끝까지 계획을 수립하고 개발하는 폭포수(Waterfall) 방법론과는 달리 개발과 함께 즉시 피드백을 받아서 유동적으로 개발하는 방법이다. 켄트 벡이 주창한 익스트림 프로그래밍(XP,Extreme Programming)과 테스트 주도 개발이 대표적이다.

11. 31p-git 관령 명령어
 - pwd
 - ls -al
 - cd (., .., 디렉토리 명, ~)
 - mkdir hello-git
 - git init★

12. git 사용의 장점★ > 25.
 - 버전관리
 - 백업
 - 협업

13. 34p-빔
 - 리눅스의 기본 편집기인 빔은 터미널에서 사용할 수 있는 대표적인 편집기이다.
 - vim test.txt
 
14. 36p-2가지 모드
 - 문서작성: 입력모드(esc -> ex모드로 바뀜)
 - 문서저장: ex모드(I, A -> 입력모드로 바뀜) -> :wq
 - :w or :write; 편집 중이던 문서를 저장한다.
 - :q or :quit; 편집기를 종료한다.
 - :wq (파일); 편집 중이던 문서를 저장하고 종료한다. 파일 이름을 함께 입력하면 그 이름으로 저장한다.
 - :q!; 문서를 저장히자 않고 편집기를 종료한다. 확장자가 .swp인 임시파일이 생긴다.
 
15. 38p-cat★
 - $ cat test.txt
 
16. 44p-깃 3가지 상태
 - 작업트리 -(git add test.txt)> 스테이지 -(git commit -m "message 1")> 저장소
 - -m: 메세지를 추가할 수 있음
 
17. 45p-status, log
 - git status: 작업트리의 상태를 볼 때
 - git log: 커밋 기록 자세히 살펴보기, 해시태그를 보는 것
 
18. 46p-git commit -am
 - commit 명령에 -am 옵션을 사용하면 스테이지에 올리고 커밋하는 과정을 한꺼번에 처리할 수 있다. 단, 이 방법은 한 번이라도 커밋한 적이 있는 파일을 다시 커밋할 때만 사용할 수 있다.

19. 48p-tracked, untracked 파일 차이 점
 - 한번이라도 commit을 하면 trackted 파일, 한적 없으면 untracked 파일
 
20. 51p-git restore 파일명
 - 작업트리에서 수정된 파일 되돌리기
 - 가장 최신이 버전 상태로 되돌려야 할 때

21. 52p-git reset HEAD 파일명
 - 스테이징에서 수정한 파일 되돌리기
 
22. 53p-git reset HEAD^(현재 HEAD ->master) 최신 커밋 취소
 - 커밋파일 되돌리기
 - git reset HEAD~3: 최신 3개의 커밋을 취소

23. 54p-git reset 해시태그
 - 특정 커밋파일 되돌리기
 - git log로 해시 확인

24. 58p-원격 저장소★
 - 지역 저장소: 지금까지 자신의 컴퓨터에서 작업하고 커밋을 저장
 - 안전을 위해 작업하는 컴퓨터가 아닌 다른 곳에 저장 공간이 필요
 - 원격 저장소: 버전 관리하는 파일들을 쉽게 백업
   * 지역 저장소가 아닌 컴퓨터나 서버에 만든 저장소
   * 지역 저장소와 연결되어 있으면서 백업과 협업이라는 중요한 역할을 함
   * 구축가능하지만 유지비용이 많이 듦(깃허브 사용)

25. 60p-깃허브로 할 수 있는 일★
 - 원격 저장소에서 깃을 사용할 수 있다(무료와 유로, 회원가입).
 - 개발자들이 많이 사용하며 오픈소스가 많다.
 - 원격 저장소만 사용 가능
 - 지역 저장소, 원격 저장소 연결 사용 가능
 - 지역 저장소를 백업할 수 있다.
   * 깃허브 원격 저장소와 사용자 컴퓨터 지역 저장소를 연결하여 동기화하면 지역 저장소를 인터넷상에서 백업할 수 있다.
 - 손쉽게 커밋할 수 있다.
 - 협업 프로젝트에 사용할 수 있다.
   * 인터넷만 가능하면 누구라도 접근 가능
   * 여러가지 협업 도구가 제공
 - 다른 사람의 소스를 살펴보고 오픈소스에 참여할 수 있다.
   * 깃허브에는 전세계 개발자들이 공개해 놓은 소스가 많다.
   * 얼마든지 소스를 내 저장소로 가져와서 분석할 수 있다(fork).★
   * 웹개발, 인공지능, 데이터 과학 등 개발의 전 분야에 걸쳐 다양한 소스가 등록
 -자기의 개발 이력을 남길 수 있다.
   * 깃허브에서 소스를 수정하고 오픈 소스에 참여해서 하는 일들은 사용자 초기 화면에서 날짜별로 모두 기록이 남는다.

26. 66p-Repository(리포지터리)를 만들 수 있음
 - https://github.com/아이디/저장소명
 - https://github.com/Paransaik/Pransaik.github.io
 
27. 66p-원격, 지역 저장소 연결
 - git remote add origin 복사한 주소 붙여넣기★
 - git remote -v
 - 주소 변경 시 git remote set-url origin 복사한 주소

28. 원격 저장소에 파일 올리기
 - 푸쉬(push): 지역 저장소의 소스를 원격으로 업로드 하는 것★
 - 풀(pull): 원격 저장소에서 지역 저장소로 다운로드 받는 것★
 - git push -u origin master
 - git pull origin master > ls -al
 
29. 78p-SSH 원격 접속
 - SSH(Secure Shell): 보안이 강화된 안전한 방법으로 정보를 교환하는 방식
 - SSH에서는 기본적으로 프라이빗 키와 퍼블릭 키를 한 쌍으로 묶어서 컴퓨터를 인증
 - 퍼블릭 키: 외부 공개 키
 - 프라이빗 키: 사용자 컴퓨터에 저장되는 키
 - SSH원격 접속은 프라이빗 키와 퍼블릭 키를 사용해 현재 사용하고 있는 기기를 깃허브에 인증하는 방식
 - SSH접속 방법을 사용하면 자동 로그인 기능을 통해 번거로움을 줄일 수 있다. 

30. 79p-SSH 원격 키 생성하기
 - ssh-keygen
 - cd ~/.ssh: 키의 위치★
 - id_rsa: 개인 키
 - id_rsa.pub: 퍼블릭 키

31. 83p-깃허브에 퍼블릭 키 전송하기
 - cat id-rsa.pub
 - 퍼블릭 키를 카피한다.
 - setting > 오른쪽 SSH and GPG Keys클릭하고 퍼블릭 키를 추가한다.
 1. 지역 저장소에서 만든 키 가운데 퍼블릭 키를 깃허브로 전송한 다음 저장
 2. 깃허브 접속 시 사용자 컴퓨터의 프라이빗 키와 깃허브 서브의 퍼블릭 키를 비교
 3. 퍼블릭 키와 프라이빗 키는 한쌍이므로 두 개의 키가 서로 맞으면 사용자 컴퓨터와 깃허브 저장소가 연결
 
32. 91p-브랜치
 - 브랜치: 나뭇가지, 버전 관리 시스템에서는 나무가 가지에서 새 줄기를 뻗듯이 여러 갈래로 퍼지는 데이터의 흐름

33. 92p-브랜치가 필요한 이유
 - 제품에 대한 사용 설명서를 깃으로 관리
 - 고객사마다 추가로 요구하는 내용이 달라짐 > 요구사항 반영시 고객사마다 제품이 달라짐 > 이에 따른 사용 설명서도 달라짐

34. 93p-해결책
 1. 처음에 저장했던 저장소 전체를 여러 개 복사
 2. 각 고객사의 이름을 붙임
 3. 각 고객사 저장소마다 버전 관리를 따로한다.
 - 깃으로 버전 관리시 기본적으로 master 브랜치가 생성
 - 사용자가 커밋할 때마다 master 브랜치는 최신 커밋을 가리킴
 - 즉, 브랜치는 커밋을 가리키는 포인터
 - 분기(branch)한다: 새 브랜치를 만들면 기존에 저장한 파일을 master 브랜치에 그대로 유지하면서 기존 파일 내용을 수정하거나 새로운 기능을 구현할 파일을 만드는 것 > master 브랜치에서 뻗어 나오는 새 브랜치를 만드는 것
 - 병합(merge)한다: 새 브랜치에 있던 파일을 원래 master 브랜치에 합치는 것 > 분기했던 브랜치를 master 브랜치에 합치는 것

35. 97p-새브랜치 만들기
 - git branch [파일명]
 - git branch: 만든 브랜치들을 볼 수 있음

36. 99p-브랜치 사이 이동하기
 - git checkout
 1. vim work.txt
 2. git commit -am "master contents 4"
 3. git log --oneline★
 4. git log --oneline --branches --graph: 각 브랜치의 커밋을 그래프로 확인★
 
37. 106p-브랜치 병합하는 3가지 방법★
 1. 서로 다른 파일 병합하기
  - git init manual-2: 새로운 디렉토리를 만들고 젖아소를 초기화
 2. 같은 파일의 다른 위치 수정시 병합
 3. 같은 파일의 같은 위치 수정시 병합(comflict)

38. 108p-브랜치 병합
 - vim work.txt
 - git add work.txt
 - git commit -m "work"
 - git branch o2
 - vi mster.txt
 - git add master.txt
 - git commit -m "master work2"
 - git checkout master
 - git merge o2
 
39. 115p-같은 문서의 같은 위치 수정했을 때 병합★★★
 - 브랜치 충돌(conflict): 각 브랜치에 같은 파일 이름을 가지고 있으면서 같은 줄을 수정한 경우 병합시 발생
 - cd ~
 - git init manual-4
 - cd manual-4
 - 문서 수정
 - git checkout master
 - git merge 02
 - 충돌 메시지(CONFLICT (content): Merge conflict in work.txt
 - 자동으로 병합되지 않기 때문에 사용자가 직접 해결
 - vim work.txt
 - 내용을 수정하고 <<<<<HEAD와 ======은 지움
 - git commit -am "merge o2 branch"
 - git log --oneline --branches --graph
 - git checkout master
 - git branch -d 02

40. 123p-git clone
 - 원격 저장소의 내용을 집, 회사의 지역 저장소로 모두 가져와야 한다.
 - 클론(clone), 클로닝(cloning) 복제한다: 원격 저장소를 지역 저장소로 똑같이 가져오는 것
 - github의 복제할 장소에서 [Clone or download] 를 선택
 - git clone 복사한 주소 git_home★
 - git log
 - git remote -v

41. 128p-여러 컴퓨터에서 원격 저장소 함께 사용하기★
 - git_home -(fetch)> github: git fetch; 병합은 따로 해야함, 파일을 가져올 때 어떤 부분이 수정 됐는지 보고 가져 옴(원래 내용과 바뀐내용의 차이를 알 수 있다.), commit이 얼마나 됐는지 알 수 있다.
 - git_home -(push)> github: git push origin master; 원격 저장소에서 필요한 파일을 다운 + 병합

 - github -(clone)> git_office; 작업 할 기존 저장소의 로컬 사본을 얻는 방법입니다.
 - github -(pull)> git_office: git pull origin master; 원격 저장소에서 새로운 커밋으로 해당 로컬 복사본 을 업데이트 하는 방법(원격저장소에 새로운 내용이 없는지) 
 
42. 135p-git fetch
 - 원격저장소의 정보를 가져오는 기능
 - pull은 원격저장소의 커밋을 가져와서 무조건 지역 저장소와 합침
 1. cd ~/git_office
 2. git fetch: 원격 저장소로부터 무언가를 가져옴
 3. 원격 저장소의 최신 커밋 정보를 가져왔지만 아직 지역 저장소를 합치지 않아 보이지 않음

43. 136p-원격 브랜치 정보 가져오기★★★(깃 패치 과정)
 1. git checkout FETCH_HEAD
 2. git checkout master
 3. git merge FETCH_HEAD

44. 142p-컨트리뷰션 그래프
 - 작업한 결과를 알 수 있음
 - 개인이 작성한 소스 코드를 커밋하는 것, 오픈 소스 프로젝트에 기역하는 커밋 모두 포함
 - 사용자들의 활동내역을 한눈에 살펴볼 수 있어 이력서 역할

45. 144p-깃허브 프로필 관리하기
 - markdown 문법 사용
 - readme: 방문자가 편하게 자기 저장소를 살펴 볼 수 있도록 안내문을 만든 파일

46. 153p-markdown 문법★★★

![OpenSource_3](https://raw.githubusercontent.com/Paransaik/Paransaik.github.io/master/_images/OpenSource_3.png)

47. 157p-이미지 삽입 방법
    - ![텍스트](./images/치노.jpg)

48. 160p-오픈 소스 프로젝트에 기여하기
 - 컨트리뷰션의 종류
   - 소스코드의 버그 수정
   - 문서의 오타 수정
   - 한글화 되어 있는 오픈 소스 일 경우 잘못 변역된 한글 수정
   - 소개글들의 변역(README)
   - 먼저 개발자에게 메일 등을 통해 변역해도 되는지 확인 후 진행

49. 167p-깃허브에 개인 블러그 만들기
 - 지킬테마(Jekyll theme)
 - .github.io
