### 1. Imgur
이미지를 볼트에 로컬로 저장하는 대신, **imgur.com**이라는 무료 이미지 호스팅 사이트에 업로드하여 원격으로 가져와 사용할 수 있도록 하는 플러그인

저장소의 용량도 줄이고, 복사&붙여넣기한 이미지를 다시 가져가 사용하는 것도 가능해진다.
![|275](https://i.imgur.com/HGywYct.png)

플러그인 설정 메뉴에서 인증된 업로드(Authenticated upload)와 익명 업로드(Anonymouse upload) 두 가지 옵션 중 하나를 선택할 수 있다.
나는 이미지의 유지나, 안정성이 훨씬 좋다는 **인증된 업로드 방식**을 사용했다.

[https://imgur.com/](https://imgur.com/) 
인증된 업로드 방식을 사용하기 위해선 imgur사이트에 회원가입을 해야한다. 그리고 Client ID를 발급 받아야 하는데, 아래 링크를 타고 들어가면 깃에 발급방법이 자세히 기재되어있다. Application name, callback URL, Email 정도만 넣으면 된다.
![|199](https://i.imgur.com/ln87dLI.png)
![|250](https://i.imgur.com/GLRSgzA.png)

발급받은 Client ID를 입력하고 **Authenticate**(인증하기) 버튼을 누르면 몇 초 뒤 웹페이지로 연결되고, **allow**버튼을 누르면 imgur 계정과 옵시디언 연결이 완료된다!
![|375](https://i.imgur.com/w8WU94v.png)


### 2. Git
효율적인 버전 관리, 멀티 디바이스 동기화 구현을 위한 깃허브 연동을 지원하는 플러그인

선행사항:
- 깃허브 설치(https://git-scm.com/)
- 깃허브 레포지토리 생성 (public or private Repository 추가)
	- Public Repository로 생성 시, '.gitignore' 파일에 비공개할 note만 따로 설정 가능
![|500](https://i.imgur.com/pBf1nGd.png)

![|500](https://i.imgur.com/N09wDcj.png)

C:\Users\yeson\Desktop\YesonObsidian\.obsidian
관리할 옵시디언 볼트 폴더에서 터미널 열어 git설정
```Shell
git init
git config --local user.name "깃허브 아이디 이름"
git config --local user.email "깃허브 이메일 이름"
```
- .gitignore파일 추가하여 git커밋에서 제외할 파일 설정
```null
.obsidian/

.obsidian/workspace-mobile.json
.obsidian/workspace.json
.obsidian/app.json

.trash/
.DS_Store
```
- 깃허브에 올리기
```shell
git add .
git commit -m "initial commit"
git branch -M main 
git remote add origin "생성한 깃허브 주소"
git push -u origin main
```
- 오류난다면 Options에서 커밋 Author를 설정했는지 확인해보기
![400](https://i.imgur.com/BgPA4Rq.png)
- 일정 시간마다 자동으로 커밋해주는 기능도 있지만 정직한 깃허브 잔디밭 관리를 위해 직접 해주기로 했다.
![500](https://i.imgur.com/ZCTlKrn.png)
- 수동 커밋은 좌측 메뉴 중 Open Git source control메뉴 눌러, 우측 커밋창에서 Staged Changes 시켜 commit, push 가능하다.
![50](https://i.imgur.com/a9CGyT6.png) ![200](https://i.imgur.com/9axrfj7.png)



### 3. Mouse Wheel Image Zoom
이미지 파일의 사이즈 조절을 마우스 휠로 간편하게 할 수 있도록 지원해주는 플러그인
![|325](https://i.imgur.com/bMdTpVB.png)
![|300](https://i.imgur.com/t2femJX.png)
플러그인 설정에서 **Trigger Key**로 사이즈 조절 활성화 단축키 설정이 가능하다. 기본으로 설정되어있는 Alt키가 제일 편한 것 같다.