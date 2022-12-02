# R Studio 설치 및 R interface 소개

- R Studio 설치
    - [https://rstudio.com/](https://rstudio.com/) 에 접속해서 다운로드
        
        상단의 다운로드를 클릭 → RStudio Desktop의 다운로드 클
        
        ![Untitled](R%20Studio%20설치%20및%20R%20interface%20소개/Untitled.png)
        
        ---
        
        ![Untitled](R%20Studio%20설치%20및%20R%20interface%20소개/Untitled%201.png)
        
        자신의 OS체제에 맞는 버전으로 다운로드 클릭 → 내려받은 설치 파일을 마우스 오른쪽 버튼 눌러서 관리자 권한으로 실행하고 설치 → 설치 과정은 기본 세팅 그대로 할 것
        
        ---
        
        ![Untitled](R%20Studio%20설치%20및%20R%20interface%20소개/Untitled%202.png)
        
        만약 자신의 OS체제가 32-bit 체제라면 스크롤을 더 내려서 구 버전으로 다운로드 할 것
        
        ---
        
        ![Untitled](R%20Studio%20설치%20및%20R%20interface%20소개/Untitled%203.png)
      
        설치 후 실행하면 4개의 창으로 구성된 아래와 같은 화면이 나옴. 각 창의 오른쪽 위 버튼으로 창을 보이거나 숨길 수 있음
        
        ---
        
        ![Untitled](R%20Studio%20설치%20및%20R%20interface%20소개/Untitled%204.png)
        
        각 창의 역할 확인을 위하여, 상단의 Tools >> Global Options  >> Pane Layout 클릭
        
        여기서 4개의 창 역할 확인 및 구성 변경 가능
        
        윗줄의 Source는 프로그램을 입력하는 창이고, 아랫줄의 Console은 결과를 확인하는 창
        
        오른쪽은 프로그램 실행 과정에서 생성된 파일이나 도움말 등을 확인할 수 있는 창으로 구성을 변경하기 위하여 체크 박스를 사용
        
        ![Untitled](R%20Studio%20설치%20및%20R%20interface%20소개/Untitled%205.png)
        
- R Studio interface 소개
    - R Studio interface 구성
    
    ![Untitled](R%20Studio%20설치%20및%20R%20interface%20소개/Untitled%206.png)
    
    ---
    
    - 사용법: 명령어 창에 작성된 명령어를 (블록) 선택한 후 명령어 창 상단의 실행버튼(RUN)을 클릭하거나 Ctrl + Enter(맥에서는 Cmd + Enter)를 누르면 다음과 같이 데이터창, 콘솔창, 플롯 창에 결과가 나타남
    
    ![Untitled](R%20Studio%20설치%20및%20R%20interface%20소개/Untitled%207.png)
    
    ---
    
    **1. 명령어 창**
    
        1) 이 창은 여러 개의 탭을 만들 수 있음. 즉, 여러 개의 스크립트를 띄워 놓고 동시에 작업 가능. 아래 사진의 상단 플러스가 표시된 그림을 누른 뒤 R Script 버튼을 누르면 스크립트 추가 가능(Ctrl + Shift + N)
    
        2) 코드 실행법: 명령어 창에 작성된 명령어를 (블록) 선택한 후 명령어 창 상단의 실행버튼(RUN)을 클릭하거나 Ctrl + Enter(맥에서는 Cmd + Enter) 누르기. 스크립트 파일의 모든 행을 한 번에 실행하고 싶으면 Ctrl + Shift + Enter
    
    ![Untitled](R%20Studio%20설치%20및%20R%20interface%20소개/Untitled%208.png)
    
    ---
    
    **2. 콘솔 창**
        
        1) 앞의 명령어 창에서 작성한 명령어를 실행시킬 때 이 창에서 분석이 이뤄지고, 분석 결과가 나타남
        
        2) 명령어 이력(History): R에서는 이전에 입력한 명령어들을 찾아볼 수 있고, 필요할 때 다시 사용 가능
        
        3) 콘솔을 사용하는 경우 위/아래 방향키를 눌러서 명령 이력을 볼 수 있음. 불러온 이력을 다시 실행하려면 엔터키 누르면 되고, 빈줄로 돌아가려면 esc키를 누르면 됨
        
        4) 만약 콘솔창에서 >가 아니라 + 가 뜬다면 그것은 스크립트 창에서 입력한 코드가 오류가 난 것임 (괄호를 닫지 않았던지 등). 이를 해결하기 위해서는 콘솔창에서 esc를 누를 것
        
    
    ![Untitled](R%20Studio%20설치%20및%20R%20interface%20소개/Untitled%209.png)
    
    ---
    
     **3. 데이터 창**
    
       Envrionment 탭을 이용해서 작업공간에 들어 있는 모든 객체를 볼 수 있으며, History 탭에서는 이전에 수행했던 명령어들을 볼 수 있음. 필요 시 이 명령어를 사용하여 명령을 반복해서 수행 가능
    
    ![Untitled](R%20Studio%20설치%20및%20R%20interface%20소개/Untitled%2010.png)
    
    ---
    
    **4. 패키지 및 그림 창**
    
        파일을 찾아보고, 사용할 패키지를 불러오거나 닫을 수 있고, 패키지를 설치하고 업데이트 할 수 있음. 또 도움말 보기를 통해서 필요한 내용을 찾아볼 수 있음. 플롯 탭에서 자신이 작업한 도표 등을 확인할 수 있음
    
        1) Zoom: 현재보타 큰 플롯을 새 창에 보여줌
    
        2) Export: 내보내기 기능. 현재 플롯을 다른 형태의 파일로 내보내는 기능. Image, PDF, Clipboard 복사 등
    
        3) 탐색: 왼쪽 방향(←), 오른쪽 방향(→) 화살표 버튼은 이전 플롯을 가져오거나 최근 생성한 플롯을 불러오는 데 사용
    
    ---
    
    ---
    
    ![Untitled](R%20Studio%20설치%20및%20R%20interface%20소개/Untitled%2011.png)
