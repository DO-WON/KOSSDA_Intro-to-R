# R 패키지와 라이브러리

- 패키지란?
    - 패키지는 다양한 함수, 명령어, 데이터들의 집합. 원하는 분석에 적합한 패키지를 찾아서 사용하는 것이 중요함. 구글링 필수!
    - R에서 기본으로 제공하는 베이스 함수나 데이터 등 외에 특정 분석이 가능하도록 여러 사람이 만들어 제공하는 함수들의 묶음인 패키지들이 존재함.
    - 패키지는 CRAN([http://cran.r-project.org](http://cran.r-project.org))에서 모든 패키지를 직접 검색하고 다운로드할 수 있음. 아래 사진에의 왼쪽의 [Packages]를 클릭하면 패키지가 만들어진 날짜 기준으로 혹은 이름 기준으로 패키지 목록을 확인이 가능하며 다운로드 역시 가능함.
        
        ![Untitled](R%20패키지와%20라이브러리/Untitled.png)
        
- 패키지 설치 방법
    - 패키지는 반드시 인터넷 환경이 조성되어야 설치 가능함
    - 패키지는 라이브러리>문서>R폴더에 저장됨
    - 경로를 확인하고 싶으면 `.libPaths()` 명령어 입력
    
    1) 명령어 직접 입력
    
    ```r
    install.packages("tidyverse")
    install.packages("ggplot2")
    
    # or
    install.packages(c("tidyverse", "ggplot2"))
    ```
    
    2)  메뉴 이용
    
    상단 [Tools] > [Install Packages] 클릭한 후 나타나는 창에 패키지 이름을 입력한 후 다운
    
    ![Untitled](R%20패키지와%20라이브러리/Untitled%201.png)
    
    ![Untitled](R%20패키지와%20라이브러리/Untitled%202.png)
    
    3) CRAN([http://cran.r-project.org](http://cran.r-project.org)) 이용
    
- 패키지 사용하기
    
    패키지를 설치한 후에 그 패키지를 이용해서 분석을 하기 위해서는 설치한 패키지를 불러와야 함
    
    1) 패키지 불러오기: 반드시 `library(패키지명)` 함수로 불러들임. R을 사용하다가 종료하고 다시 시작했을 경우에도 다시 `library(패키지명)`을 실행하여야 패키지 내의 여러 함수나 데이터들을 쓸 수 있음
    
    ```r
    # install.packages("tidyverse")
    # install.packages("ggplot2")
    library("tidyverse")
    library("tidyverse")
    
    # update.packages("패키지명") # 설치되어 있는 해당 패키지 업데이트
    # installed.packages()       # 어떤 패키지들이 설치되어 있는지 확인
    # remove.packages("패키지명") # 해당 패키지 삭제
    ```
    
    ![ **`tidyverse`**](R%20패키지와%20라이브러리/Untitled%203.png)
        
    2) 패키지 사용하여 분석
