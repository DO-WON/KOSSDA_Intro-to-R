# 작업 공간(workspace) 만들기

- 작업 공간이란 기본적으로 R의 분석이 이루어지는 공간(폴더)이라고 생각하면 됨. 이곳에 유저가 만든 모든 객체(데이터프레임, 함수, 리스트 등)들이 존재함.
- Stata나 SPSS 등은 하나의 데이터셋에 대해서 통계 분석을 수행하지만, R은 작업 공간 내에 여러 개의 데이터프레임과 다른 객체들이 존재하며, 서로 다른 데이터프레임의 변수 간의 분석도 가능함.
- 처음 `RStudio`을 실행하면 기본 작업 공간에서 열림. 그러나 효율적인 작업을 위해서는 작업 공간을 자신이 별도로 지정한 폴더로 설정해주는 것이 좋음. 여러 개의 프로젝트(별도의 통계분석)를 수행할 때 각각의 프로젝트를 별도의 작업 폴더를 지정하여 사용하는 것을 추천.

### 작업 공간 예시

![Untitled](작업%20공간(workspace)%20만들기/Untitled.png)

- 분석을 마친 후 R을 종료할 때 작업 공간의 내용을 저장하면, 다음 작업 시에 저장된 작업 공간을 그대로 불러와서 사용할 수 있음.

---

- 자신이 지정한 폴더로 작업 공간을 바꿔주는 방법
    
    RStudio 실행 → 상단의 [File] → [New Project] 클릭하면 아래와 같은 창이 나타남
    

![Untitled](작업%20공간(workspace)%20만들기/Untitled%201.png)

위의 사진에서 **New Directory**를 클릭 후 **New Project**를 클릭하면 아래와 같은 화면이 나옴

![Untitled](작업%20공간(workspace)%20만들기/Untitled%202.png)

위 사진과 같이 

1) 디렉토리 이름(영어로 입력! 한글로 입력시 충돌하여 오류가 남)을 자유롭게 입력한 뒤

2) 작업 경로 설정해 줌. 즉, practice로 설정한 나의 프로젝트가 어느 위치에 있을지를 설정하는 것 

3) 하단의 Create Project 버튼을 누르면 완료

그럼 아래와 같이 내가 설정한 경로를 따라 practice 폴더가 생성되었고, 여기에 practice 프로젝트가 형성됨

![Untitled](작업%20공간(workspace)%20만들기/Untitled%203.png)

- 이제 작업공간이 생성되었음. 내가 생성한 작업공간 안에 있는 프로젝트(**.Rproj 확장자 파일**)를 더블클릭하여 실행!

---

그러면 아래와 같이 내 작업 공간을 확인할 수 있음

![Untitled](작업%20공간(workspace)%20만들기/Untitled%204.png)

상단의 플러스와 흰 페이지가 들어간 아이콘을 눌러 `R script`를 생성하여 내가 원하는 작업을 시작하면 됨!

![Untitled](작업%20공간(workspace)%20만들기/Untitled%205.png)

R script의 기본 이름은 Untitled이며, 아직 내 작업 공간에 저장되지 않은 상태임. 내가 작성한 스크립트를 보기 쉽게 관리하고 다음에 작업할 때 또 불러오기 위해서는 저장이 필요함.

내가 저장할 script를 클릭한 후 Ctrl S를 누르거나 [File]의 [Save] 혹은 [Save as] 클릭

스크립트 명은 디렉토리 명과 달리 한글로 해도 별 상관은 없으나 되도록이면 영어로 추천!

![Untitled](작업%20공간(workspace)%20만들기/Untitled%206.png)

![script1 이라는 이름으로 저장 ](작업%20공간(workspace)%20만들기/Untitled%207.png)

script1 이라는 이름으로 저장 (R script 확장자: `.R`)

그러면 아래와 같이 스크립트명이 내가 지정한 이름으로 저장이 되고, 내 작업공간에도 저장이 된 것을 확인할 수 있음

![Untitled](작업%20공간(workspace)%20만들기/Untitled%208.png)

작업을 마친 후 이 작업을 종료하기 전에 스크립트를 저장을 하고(마치 한글파일 작업 완료 후 저장하듯이), 다음에 내 작업을 불러와 이어서 작업하려면 내가 설정한 작업공간으로 들어가서 프로젝트 파일(.Rproj)을 눌러 실행시키면 됨.

- 참고) 작업 공간 관련 함수 `getwd()` : 현재 작업 공간의 경로를 보여줌

![Untitled](작업%20공간(workspace)%20만들기/Untitled%209.png)
