# Introduction to R

사람: Do Won Kim, Hyowon Kim
상태: KOSSDA TA

### Note

이 페이지는 KOSSDA 방법론 강좌 수강생들을 위한 R 기초 튜토리얼입니다. 

### Table of Contents

1. **Prerequisites** 
    - 1-1. ***Installing R RStudio***
        
        [R 설치하기](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/R%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%E1%84%92%E1%85%A1%E1%84%80%E1%85%B5%20ba5adfbe9cd2414fb0365b1b9469ecfb.md)
        
    - 1-2. ***Installing RStudio & R interface***
        
        [R Studio 설치 및 R interface 소개](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/R%20Studio%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8E%E1%85%B5%20%E1%84%86%E1%85%B5%E1%86%BE%20R%20interface%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%2073fc48ab89ee45449d4cbc4ad6046aa6.md)
        
    - 1-3. ***Creating a Workspace***
        
        [작업 공간(workspace) 만들기](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/%E1%84%8C%E1%85%A1%E1%86%A8%E1%84%8B%E1%85%A5%E1%86%B8%20%E1%84%80%E1%85%A9%E1%86%BC%E1%84%80%E1%85%A1%E1%86%AB(workspace)%20%E1%84%86%E1%85%A1%E1%86%AB%E1%84%83%E1%85%B3%E1%86%AF%E1%84%80%E1%85%B5%203658928eac0f441c8faf4bdada2971dd.md)
        

---

2. R 기본 문법 **Basic programming in R** 
    - 2-1. R 문법의 기초 ***Communicating in R language***
        
        R은 기본적으로 함수형 언어입니다. 함수는 `함수명()`의 형태로 되어 있고, `( )`안에는 필요한 인자들을 입력할 수 있습니다. 인자(argument)란 특정 함수가 실행되는 조건들을 지정해주는 함수의 요소라고 생각하시면 됩니다. (e.g. `lm(Y~X, data)`)
        
        한편, 어떤 인자들은 반드시 괄호 안에 입력해주어야 하는 반면, 어떤 인자는 입력하지 않아도 되는데, 이를 기본인자라고 합니다. 기본인자는 함수를 정의할 때 특정 조건이 미리 지정되어 있는 것이므로 특별히 다른 조건을 원하지 않는다면 생략해도 됩니다. (e.g. `q()` :R의 종료 명령어) 
        
        함수의 기능과 필요한 인자를 찾기 위해 R의 도움말을 참고하시면 됩니다. 알고자 하는 함수에 대한 도움말은 콘솔창에서 `help(함수명)` 또는 `?함수명` 을 입력하면 됩니다. (e.g. `help(lm)` 또는 `?lm`) 
        
        ---
        
        다음은 R에서 객체(object) 또는 변수를 만들고 사용하는 방법을 알려 드리겠습니다. R에서 객체란, 데이터가 담겨 있는 메모리의 주소 값, 즉 데이터를 담는 그릇입니다. R에게 분석해야 할 데이터를 줄 때 객체/변수라는 그릇에 담아서(=할당하여) 준다고 생각하시면 됩니다. (e.g.`객체/변수 이름 <- 저장할 값`) 
        
        📌 “할당”한다는 것의 의미: 값을 객체에 저장한다는 것. 영어로는 assign (지정, 할당). 할당자로는 `<-`또는 `=` 을 사용함. 
        
        ![`변수 <- Data`](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled.png)
        
        `변수 <- Data`
        
        - 객체/변수의 이름을 정할 때의 주의사항:
            - 이름은 한글, 영어, 숫자 등이 가능하지만 반드시 첫 글자는 문자여야 함
            - 이름이 영어일 경우 소문자와 대문자는 다른 글자로 인식함
        
        객체에 값을 할당하는(=변수에 값을 담는) 연습을 해봅시다. 
        
        ```r
        var1 <- 1 # var1 이라는 변수에 숫자 1 담기
        var1 # 출력하여 확인 
        var2 <- 2 # var2 라는 변수에 숫자 2 담기
        var2 # 출력하여 확인
        age <- 20 # age 라는 변수에 숫자 20 담기
        Age <- 50 # Age라는 변수에 숫자 50 담기
        					# R is case sensitive ; age and Age are different
        var3 <- "대학원생" # var3 변수에 글자 담기. 
        									# "" 주의
        var4 <- as.Date("2022-12-01") # 날짜 데이터 담기
        var5 <- "Hello world" # 문자열 데이터 담기
        ```
        
        - new line by ; (semicolon)
        
        ```r
        Name <- "Kossda" ; Age <- 25; City <- "Seoul" 
        Name 
        Age
        City 
        ```
        
    - 2-2. 데이터 유형 ***Data type***
        - 변수에 담을 수 있는 데이터 유형
            - 숫자형 데이터(numeric)
                
                ```r
                x <- 100 # assign a number to the variable named x 
                class(x) # check the class of x 
                class(5,000) #에러 확인! 숫자 중에는 ,(콤마) 가 없음
                
                #연산 가능
                2+3 
                2*3
                2/3
                2^3
                10%%3
                # square root
                sqrt(2)
                # round to two decimal places 
                round(1.41421, 2) 
                # round down to nearest integer
                floor(1.41421)
                # absolute value
                abs(-2) 
                # exponential 
                exp(2) 
                # logarithm
                log(2)  
                
                # assign to a variable and use these variables to calculate
                height <- 170
                weight <- 60 
                # BMI = weight / height^2 (in metre) 
                BMI <- weight / (height/100)^2
                
                ```
                
            - 문자형 데이터(character/string/text)
                
                참고) useful packages for dealing with texts/strings/characters in R : `stringr`, `tidytext`
                
                ```r
                class(5) #데이터유형 확인
                class("5")
                class("2022-12-01") #날짜 같지만 문자형
                class("Hello World!") #문자열도 문자형
                
                # assign to a variable 
                greeting <- "Hello World!" 
                greeting 
                
                x = "100" 
                class(x) # character type: let's convert it to numeric type
                as.numeric(x) # converts to numeric type 
                class(x) # you should assign it to x to update
                x = as.numeric(x)
                class(x) 
                
                x = "kossda" 
                as.numeric(x) # fails
                ```
                
            - 날짜형 데이터 `as.Date()`
                
                참고) 날짜형 데이터를 다루는데 특화된 패키지: `lubridate`
                
                ```r
                date1 <- as.Date("2022-12-25")
                date2 <- as.Date("2022-12-01")
                date1 - date2  #날짜 연산 가능
                difftime(date1, date2)
                ```
                
            - NA형과 NULL형
                - NA(Not Applicable)형: 학년 변수에 1, 2, 3, 4 등의 값들이 들어와야 하는데 “손흥민”같은 문자형 값이 들어온 경우.
                - NULL(Not Available)형: 데이터 값이 아예 없다는 말. 즉 비어 있음. NA와 달리 연산을 하면 NULL값을 자동으로 제외시키고 연산을 진행함.
                
                ```r
                no1 <- 3
                no2 <- NA
                no1 + no2 # 연산 결과를 NA로 만들어 버림
                
                sum(1, 2, NA)
                sum(1, 2, NULL) # NULL값을 자동으로 제외시키고 연산을 진행함
                
                x <- NA
                sum(1, 2, x)
                sum(1, 2, x, na.rm=TRUE) #NA값 제거
                x[is.na(x)] <- 0 # NA값을 0으로 바꿈
                sum(1, 2, x)
                ```
                
            - 논리형 데이터(logical: True or False)
        - 변수 유형
            
            데이터를 분석할 때는 변수의 유형 및 속성에 따라 분석기법이 달라짐
            
            | 변수 유형 | 예시 | 변수 속성 | R에서 분류 |
            | --- | --- | --- | --- |
            | 명목형(nominal) | 성별: 남성, 여성 | categorical | factor(범주변수) |
            | 순서형(ordinal) | 건강상태: poor, good, excellent | ordered/categorical | factor(범주변수) |
            | 연속형(continuous) | 연령: 22, 34, 45 | numerical | numerical(수량변수) |
            
            ```r
            diabetes <- c(1, 2, 1, 1)
            diabetes <- factor(diabetes) #범주변수로 처리
            
            #알파벳 순서로 1=excellent, 2=good, 3=poor로 정함
            status <- c("poor", "good", "excellent", "poor")
            status <- factor(status)  
            
            #순서를 1=poor, 2=good, 3=excellent로 정함
            status <- factor(status, levels=c("poor", "good", "excellent"))
            status <- factor(status, levels=c("poor", "good", "excellent"), order=TRUE)
            ```
            
    - 2-3. 데이터 구조 ***Data structure***
        
        R에서 취급하는 데이터는 여러 구조를 가질 수 있습니다. 가장 단순한 형태부터, 실제로 분석에서 많이 쓰이는 형태까지 훑어 봅시다. 
        
        - **벡터(Vector)**
            - 숫자 또는 문자의 나열
            - 하나의 벡터에는 반드시 데이터 유형이 같은 값들만 들어가야 함
            
            ```r
            v1 <- 1:5 
            v2 <- c(6:10) # c() : combine 
            v3 <- seq(from = 1, to = 10, by = 2)
            v4 <- c("a", "b", "c")
            v5 <- rep(0, times = 10) 
            
            var1 <- c(1, 2, "3")
            class(var1)
            
            # Indexing을 이용한 벡터의 원소 접근 및 연산
            v7[1] <- v1[1] + v1[3]; v7 # v7 is not defined yet! 
            v7 <- NULL # empty object 
            v7[1] <- v1[1] + v1[3]; v7
            v7[2] <- v1[1] / 0; v7
            v7[3] <- 0/0; v7
            v7 <- v7[-1]; v7 # omit the first element 
            
            # 문자열 벡터
            fruit <- c("banana", "apple", "pine", "tree")
            fruit
            grep('p', fruit)
            grep('p', fruit, value = T)
            paste(fruit[3], fruit[2], sep = "") 
            substr(fruit[1], 3, 6)
            ```
            
        - **행렬(Matrix)**
            - 여러 개의 벡터로 구성된, 가로 X 세로 형태의 행렬
            - 벡터와 마찬가지로 동일한 유형의 데이터가 들어가야 함
            
            ```r
            ?matrix 
            mat1 <- matrix(c(1, 3, 6, 9, 12, 15), nrow = 2, ncol = 3); mat1 
            mat2 <- matrix(c(1, 3, 6, 9, 12, 15), nrow = 2, ncol = 3, byrow = T); mat2 
            
            v8 <- mat.or.vec(nr = 3, nc = 2); v8 
            v9 <- mat.or.vec(2, 0); v9 
            v10 <- as.vector(mat2); v10 # as.vector() : make the object into 'vector'
            mat3 <- matrix(v10, nrow = 3, ncol = 2); mat3
            
            ### vector를 이용한 matrix 생성
            mat4 <- rbind(v1, v2, v3); mat4
            mat5 <- cbind(v1, v2, v3); mat5
            mat6 <- mat4 %*% mat5; mat6 # matrix multiplication 
            mat7 <- mat4 * mat4; mat7 # Kronecker product ( Different from %*% !! )
            
            ### indexing / 차원 확인
            m <- matrix(1:9, 3, 3); m 
            m[, 1:2]
            m[c(1,3),]
            m[2:3, 2:3]
            dim(m)
            length(m)
            length(v1)
            ```
            
        - **배열(Array)**
            - 매트릭스형을 1층, 2층, 3층처럼 높이 쌓는 것
            - 벡터, 매트릭스와 마찬가지로 동일한 유형의 데이터가 들어가야 함
            
            ```r
            array1 <- array(c(1:12), dim=c(2,2,3)) # dim=c(행, 열, 높이)
            array1[1, 1, 1]
            array1[1, 1, 2]
            array1[1, 2, 2]
            ```
            
        - **리스트(List)**
            - 서로 다른 데이터 유형들을 묶어서 하나의 리스트로 저장 가능
            - 주로 텍스트 분석에서 많이 사용
            - 리스트 = 큰 방
                - 변수 = 작은 방
                    - 값
            
            ```r
            list1 <- list(NO= c(7, 10, 8), 
            							NAME=c("손흥민", "해리케인", "페르난데스"), 
            							BIRTH=c("1992-07-08", "1993-07-28", "1994-09-08"))
            
            list1 # 작은 방: NO, NAME, BIRTH
            list1$NO # list1의 NO라는 변수(작은방) 출력해라 
            list1[["NO"]] # 같은 명령어 [[ ]]
            list1[["NAME"]][1] # list1의 NAME이라는 이름의 작은 방에서 첫 번째 요소를 출력해라 
            list1$birth
            list1[3]
            
            list2 = list(c(1,5,3), matrix(1:6, nrow=3), c('hello', 'world'))
            list2
            list2[[1]] ; mode(list2[[1]])
            list2[1] ; mode(list2[1])
            list2[[2]][2,1]
            list2[2][2,1] # Error ! 
            list2[[2]][2] <- 'world' ; list2[[2]]
            list2[c(1,3)]
            ```
            
        - **데이터 프레임(Data Frame)**
            - 다양한 유형의 데이터들을 저장. 가장 많이 사용하는 형태임.
            - 엑셀 표라고 생각하면 됨.
            
            | NO | NAME | BIRTH |
            | --- | --- | --- |
            | 7 | 손흥민 | 1992-07-08 |
            | 10 | 해리케인 | 1993-07-28 |
            | 9 | 홀란드 | 2000-07-21 |
            
            ```r
            no <- c(7, 10, 9)
            name <- c("손흥민", "해리케인", "홀란드")
            birth <- c("1992-07-08", "1993-07-28", "2000-07-21")
            player <- data.frame(NO=no, NAME=name, BIRTH=birth)
            player 
            # or 
            data.frame(list1)
            
            m
            data <- data.frame(m); data # Difference btw 'matrix' and 'dataframe' ? 
            colnames(data)
            rownames(data) <- c("N1", "N2", "N3")
            data
            data <- data.frame(data, "class" = c(1, 1, 3))
            data
            data[, 4] # data[row index, column index]
            data$class # data$variable
            ```
            
    - 2-4. R 패키지와 라이브러리 ***R packages and libraries***
        - 패키지란?
            - 패키지는 다양한 함수, 명령어, 데이터들의 집합. 원하는 분석에 적합한 패키지를 찾아서 사용하는 것이 중요함. 구글링 필수!
            - R에서 기본으로 제공하는 베이스 함수나 데이터 등 외에 특정 분석이 가능하도록 여러 사람이 만들어 제공하는 함수들의 묶음인 패키지들이 존재함.
            - 패키지는 CRAN([http://cran.r-project.org](http://cran.r-project.org))에서 모든 패키지를 직접 검색하고 다운로드할 수 있음. 아래 사진에의 왼쪽의 [Packages]를 클릭하면 패키지가 만들어진 날짜 기준으로 혹은 이름 기준으로 패키지 목록을 확인이 가능하며 다운로드 역시 가능함.
                
                ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%201.png)
                
        - 패키지 설치 방법
            - 패키지는 반드시 인터넷 환경이 조성되어야 설치 가능함
            - 패키지는 라이브러리>문서>R폴더에 저장됨
            - 경로를 확인하고 싶으면 .libPaths() 명령어 입력
            
            1) 명령어 직접 입력
            
            ```r
            install.packages("tidyverse")
            install.packages("ggplot2")
            
            or
            install.packages(c("tidyverse", "ggplot2"))
            ```
            
            2)  메뉴 이용
            
            상단 [Tools] > [Install Packages] 클릭한 후 나타나는 창에 패키지 이름을 입력한 후 다운
            
            ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%202.png)
            
            ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%203.png)
            
            3) CRAN([http://cran.r-project.org](http://cran.r-project.org)) 이용
            
        - 패키지 사용하기
            
            패키지를 설치한 후에 그 패키지를 이용해서 분석을 하기 위해서는 설치한 패키지를 불러와야 함
            
            1) 패키지 불러오기: 반드시 library(”패키지명”) 함수로 불러들임. R을 사용하다가 종료하고 다시 시작했을 경우에도 다시 library(”패키지명”)을 실행하여야 패키지 안에 여러 함수나 데이터들을 쓸 수 있음. 
            
            ```r
            #install.packages("tidyverse")
            #install.packages("ggplot2")
            library("tidyverse")
            #library("tidyverse")
            
            # update.packages("패키지명") # 설치되어 있는 해당 패키지 업데이트
            # installed.packages()       # 어떤 패키지들이 설치되어 있는지 확인
            # remove.packages("패키지명”) # 해당 패키지 삭제
            ```
            
            ![ **`tidyverse`**](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%204.png)
            
             **`tidyverse`**
            
            2) 패키지 사용하여 분석
            
        

---

3. 데이터 다루기 **Data Management** 
    - 3-1. 내장데이터 불러오기 ***Loading build-in data***
        
        R에는 누구나 사용가능한 **내장 데이터**들이 있습니다. 가장 대표적인 몇 가지 내장 데이터를 불러오는 방법을 알려 드리겠습니다. 이 데이터들은 실습 내내 종종 등장하므로 데이터가 어떻게 생겼는지, 어떤 변수들이 있는지 등에 익숙해 지시길 바랍니다. 
        
        먼저, `data()`를 통해 내장 데이터를 불러올 수 있습니다. 이 함수 안에는 데이터명을 기입해 주세요. 
        
        ```r
        # most used built-in datasets: e.g. mtcars 
        data("mtcars")
        ```
        
        `mtcars`데이터(Motor Trend Car Road Tests)는 1974년 Motor Trend US magazine에서 추출한 32종의 자동차의 여러 특성들을 담은 데이터입니다. 데이터 프레임은 32개의 케이스(행)과 11개의 변수(열)로 이뤄져 있습니다. 
        
        | 변수 | 의미 |
        | --- | --- |
        | mpg | Miles/(US) gallon |
        | cyl	 | Number of cylinders |
        | disp	 | Displacement (cu.in.) |
        | hp	 | Gross horsepower |
        | drat	 | Rear axle ratio |
        | wt | Weight (1000 lbs) |
        | qsec	 | 1/4 mile time |
        | vs	 | Engine (0 = V-shaped, 1 = straight) |
        | am	 | Transmission (0 = automatic, 1 = manual) |
        | gear	 | Number of forward gears |
        | carb	 | Number of carburetors |
        
        ```r
        # 데이터가 어떻게 생겼는지 확인하는 방법: 
        # (1) head(): 데이터프레임의 상위 몇 개 행들을 출력
        head(mtcars)
        
        # (2) summary()
        summary(mtcars) 
        
        # (3) tidyverse 패키지의 glimpse()
        library(tidyverse)
        glimpse(mtcars)
        ```
        
        패키지 내에 내장되어 있는 데이터들도 있습니다. 먼저 패키지를 설치한 후, `library()`를 통해 패키지를 사용가능하도록 불러옵니다. 그 다음은 똑같은 방식으로 `data()`를 통해 패키지 내장 데이터를 불러와 주세요. 저희는 gapminder라는 패키지를 설치하고, 내장 데이터인 `gapminder`를 불러와 볼게요. 
        
        ```r
        # datasets within packages 
        install.packages("gapminder") 
        library(gapminder)
        data("gapminder")
        ```
        
        **`gapminder`** 데이터프레임에는 총 여섯 개의 변수가 있습니다. 
        
        | 변수 | 의미 |
        | --- | --- |
        | country | 국가 |
        | continent | 대륙 |
        | year | 연도 |
        | lifeExp | 기대수명 |
        | pop | 총 인구 수 |
        | gdpPercap | 1인당 국내총생산 (단위: international dollars - "a hypothetical unit of currency that has the same purchasing power parity that the U.S. dollar had in the United States at a given point in time") |
        
        ```r
        # 데이터가 어떻게 생겼는지 확인해 보세요. 
        head(gapminder) 
        summary(gapminder) 
        ```
        
    - 3-2. 데이터 저장하기(내보내기), 불러오기 ***Exporting and importing data***
        
        R에서는 데이터프레임을 SAS, SPSS, Stata, 그리고 csv 등 다양한 확장자를 지닌 데이터 파일로 내보내거나, 혹은 다양한 확장자를 지닌 데이터 파일을 R에 데이터프레임 형태로 불러올 수 있습니다. 데이터를 내보내고(export), 불러올(import) 때에는  `haven`패키지와 `readr`패키지를 대표적으로 사용합니다. 예시는 아래와 같습니다. 실습에서는 dta확장자를 지닌 Stata파일로 내보내고, 다시 그 파일을 R로 불러오는 연습을 함께 해보겠습니다. 
        
        ```r
        # The easiest way to get haven is to install the whole tidyverse:
        install.packages("tidyverse")
        
        # load "haven" package
        library(haven)
        
        # SAS
        write_sas(mtcars, "mtcars.sas7bdat") # SAS 파일로 내보내기
        read_sas("mtcars.sas7bdat") # SAS 파일을 불러오기 
        
        # SPSS
        write_sav(mtcars, "mtcars.sav") # SPSS 파일로 내보내기
        read_sav("mtcars.sav") # SPSS 파일을 불러오기 
        
        # Stata
        write_dta(mtcars, "mtcars.dta") 
        read_dta("mtcars.dta")
        ```
        
        데이터를 불러왔는데 mtcars 내장 데이터(원본)와 조금 다릅니다. 내장 데이터에는 행의 이름(row names)이 각 자동차 종류였습니다. 즉, “자동차 종류”가 따로 변수로 있지 않았습니다. 
        
        ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%205.png)
        
        ```r
        # check row names 
        rownames(mtcars) 
        ```
        
        따라서 먼저 mtcars 원본 데이터에 “car”이라는 이름을 지닌 새로운 변수를 만들어 줍시다. 위에서 확인한 rownames(mtcars)를 `mtcars`데이터프레임의 새로운 변수 “car”로 할당을 해줍니다. 
        
        ```r
        mtcars$car = rownames(mtcars) 
        head(mtcars) # check 
        ```
        
        ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%206.png)
        
        car 변수가 잘 생성됐음을 확인할 수 있습니다. 이렇게 car 변수를 새로 만들어준 `mtcars`데이터를 stata 파일로 내보낸 후, 다시 불러와 봅시다. 
        
        ```r
        write_dta(mtcars, "mtcars.dta") 
        read_dta("mtcars.dta")
        ```
        
        read_dta() 함수를 통해 불러왔을 때 데이터가 console 창에 잘 뜨네요. 하지만 주의해야 할 점은 이 데이터는 console에 뜨기만 할 뿐, RStudio의 객체(object)로 저장된 것은 아니라는 점입니다. 따라서 객체에 따로 할당(assign)을 해주어야 합니다. `new_mtcars`라는 이름을 지닌 데이터로 할당을 해줍시다. 
        
        ```r
        new_mtcars = read_dta("mtcars.dta")
        ```
        
        ![new_mtcars로 할당이 잘 되었다면, RStudio의 Environment 창에 잘 불러와 졌음을 확인할 수 있습니다. ](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%207.png)
        
        new_mtcars로 할당이 잘 되었다면, RStudio의 Environment 창에 잘 불러와 졌음을 확인할 수 있습니다. 
        
        이렇게 외부 확장자를 지닌 데이터를 불러올 때에는 새로운 객체로 저장을 해주셔야만, 이 데이터프레임을 사용할 수 있습니다.  
        
        데이터를 불러올 때 더 쉬운 방법은 file 창에서 불러오고 싶은 데이터를 클릭하고, Import Dataset 버튼을 클릭하여 불러오는 것입니다. 
        
        ![참고: 이렇게 쉽게 데이터를 불러오려면, 불러오고자 하는 데이터가 R 프로젝트 폴더 안에 들어 있어야겠죠? 프로젝트 관리의 중요성이 여기서 나옵니다. 동일한 프로젝트 폴더(디렉토리) 안에 모든 파일들을 넣고 관리하시길 바랍니다. ](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%208.png)
        
        참고: 이렇게 쉽게 데이터를 불러오려면, 불러오고자 하는 데이터가 R 프로젝트 폴더 안에 들어 있어야겠죠? 프로젝트 관리의 중요성이 여기서 나옵니다. 동일한 프로젝트 폴더(디렉토리) 안에 모든 파일들을 넣고 관리하시길 바랍니다. 
        
        ![미리보기 창이 뜨고, 하단에 Code Preview가 뜹니다. `library(haven)`을 통해 haven 패키지를 로드한 후, `read_dta()` 함수를 통해서 데이터를 불러와 mtcars라는 객체로 저장해주는 코드입니다. 이 코드를 복사하여 R Script에 옮기거나, 우측 하단의 Import 버튼을 클릭하여 그대로 시행해 주시면 됩니다. ](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%209.png)
        
        미리보기 창이 뜨고, 하단에 Code Preview가 뜹니다. `library(haven)`을 통해 haven 패키지를 로드한 후, `read_dta()` 함수를 통해서 데이터를 불러와 mtcars라는 객체로 저장해주는 코드입니다. 이 코드를 복사하여 R Script에 옮기거나, 우측 하단의 Import 버튼을 클릭하여 그대로 시행해 주시면 됩니다. 
        
        다음은 `readr`패키지를 사용하여 csv, 엑셀 파일 등을 불러오고 내보내는 연습을 해봅시다. 
        
        ```r
        # load "readr" package
        library(readr)
        
        # CSV
        write_csv(mtcars, "mtcars.csv") # mtcars 데이터프레임 객체를 mtcars.csv라는 이름을 가진 csv 파일로 내보내라 
        new_mtcars2 <- read_csv("mtcars.csv") # mtcars.csv 파일을 R에 불러 들여와 new_mtcars2라는 이름을 가진 데이터프레임으로 저장해라 
        ```
        
    - 3-3. 데이터 전처리 ***Data wrangling & pre-processing: Base functions and Tidyverse***
        
        분석하고자 하는 데이터를 불러온 다음에는 데이터가 어떻게 생겼는지를 파악하는 작업이 필요하며, 이와 관련해서는 3-1. 내장데이터 불러오기 파트에서 세 가지의 방법을 알려드렸습니다. 이번에는 `mtcars`만큼이나 유명한 내장데이터인 `iris` 데이터를 불러와 주세요. 
        
        ```r
        # built-in data: "iris" 내장 데이터 불러오기 
        data("iris")
        
        # 데이터가 어떻게 생겼는지 살펴봅니다. 
        summary(iris) 
        str(iris)
        glimpse(iris) # tidyverse 
        
        # 범주형 변수의 경우, table() 함수를 통해 빈도를 확인합니다. 
        table(iris$Species)
        ```
        
        데이터가 어떻게 생겼는지 확인한 후에는, 분석에 용이한 형태로 원 데이터(raw data)를 가공하는 작업이 필요합니다. 이를 데이터 전처리(data pre-processing)이라고 합니다. R에서 기본으로 제공하는 base 함수들을 활용한 전처리를 먼저 배우고, `tidyverse` 패키지를 활용한 간편한 전처리를 배우도록 하겠습니다. 
        
        **Indexing: 데이터프레임에서 원하는 행, 열 추출하기** 
        
        - Base syntax in R
            
            기본 문법은 다음과 같습니다: `데이터프레임[ 행 ,  열 ]`. 먼저 관심 케이스(=행)을 추출하는 방법을 연습해 봅시다. 
            
            ```r
            # iris 데이터에서 첫 번째 행을 추출하라
            iris[1,]
            
            # 첫 번째부터 다섯 번째까지의 행을 추출하라
            iris[1:5, ] # : = ~ 
            
            # 첫 번째, 세 번째, 다섯 번째 행을 추출하라
            iris[c(1, 3, 5), ] # c() = combine()
            
            # 조건부 추출: which() 함수 사용 
            	# (1) Sepal.Length가 평균 미만인 행들을 추출하라 
            iris[which(iris$Sepal.Length < mean(iris$Sepal.Length)),]
            
            	# (2) Sepal.Width가 평균 이상인 행들을 추출하라
            iris[which(iris$Sepal.Width >= mean(iris$Sepal.Width)),]
            
            	# (3) Species가 setosa인 행들을 추출하라
            iris[which(iris$Species == "setosa"),]
            		# remark: = vs. == 
            
            # 조건부 추출: subset() 사용 
            	# (1) Sepal.Length가 평균 미만인 행들을 추출하라 
            subset(iris, iris$Sepal.Length < mean(iris$Sepal.Length))
            
            	# (2) Sepal.Width가 평균 이상인 행들을 추출하라
            subset(iris, iris$Sepal.Width >= mean(iris$Sepal.Width))
            
            	# (3) Species가 setosa인 행들을 추출하라
            subset(iris, iris$Species == "setosa")
            ```
            
            <aside>
            🧑🏻‍💻 quiz
            
            Species가 setosa가 **아닌** 애들을 추출하고 싶다면?
            
            ```r
            iris[-which(iris$Species == "setosa"),]
            
            subset(iris, iris$Species != "setosa")
            ```
            
            </aside>
            
            다음은 관심 변수(=열)를 추출하는 방법을 연습하겠습니다. 
            
            ```r
            # iris 데이터에서 첫 번째 열을 추출하라
            iris[,1]
            
            # 첫 번째부터 다섯 번째까지의 열을 추출하라
            iris[, 1:5]  
            
            # 첫 번째, 세 번째, 다섯 번째 열을 추출하라
            iris[, c(1, 3, 5)]
            
            # 변수명을 알고 있는 경우: Sepal 관련 변수들만 추출하라
            iris[, c("Sepal.Length", "Sepal.Width")] 
            
            # subset() 함수를 사용할 수도 있습니다.
            subset(iris, select=c(Sepal.Length, Sepal.Width))
            
            # 만약 특정 변수만을 보고 싶다면: 데이터프레임$변수
            iris$Species 
            ```
            
            데이터프레임에서 원하는 행과 열을 각각 indexing하여 추출하는 방법을 연습했습니다. 이번에는 행과 열을 동시에 indexing해봅시다. 
            
            ```r
            # iris 데이터에서 첫 번째 행과 다섯 번째 열을 추출하라
            iris[1,5]
            
            # 첫 번째부터 다섯 번째까지의 행과 첫 번째와 다섯 번째 열을 추출하라
            iris[1:5, c(1,5)]  
            
            # Species가 setosa인 행들의 Sepal 관련 변수들 + Speicies변수만 추출하라
            iris[which(iris$Species=="setosa"), c("Sepal.Length", "Sepal.Width", "Species")]
            ```
            
        - `Tidyverse`
            
            `tidyverse`패키지를 사용할 경우 base 함수를 사용하는 것보다 특정 조건을 갖는 행과 열을 더욱 효율적으로 추출할 수 있습니다. 행을 추출할 때에는 `filter()` 함수를, 열을 추출할 때에는 `select()` 함수를 사용합니다. 
            
            ```r
            # iris 데이터에서 행 추출하기
            	# (1) Sepal.Length가 평균 미만인 행들을 추출하라 
            iris %>% 
            	filter(Sepal.Length < mean(Sepal.Length))
            
            	# (2) Sepal.Width가 평균 이상인 행들을 추출하라
            iris %>% 
            	filter(Sepal.Width >= mean(Sepal.Width))
            
            	# (3) Species가 setosa인 행들을 추출하라
            iris %>% 
            	filter(Species == "setosa")
            
            # 열 추출하기 
            	# (1) Species 열만 추출하라
            iris %>%
            	select(Species)
            
            	# (2) Sepal 관련 변수들만 추출하라
            iris %>%
            	select(Sepal.Length, Sepal.Width) 
            	
            	# (3) Species 빼고 나머지 변수들을 다 추출하라
            iris %>%
            	select(-Species)
            
            	# (4) Sepal 관련 변수들을 제외한 나머지를 다 추출하라
            iris %>%
              select(-c(Sepal.Length, Sepal.Width))
            
            # Species가 setosa인 행들의 Sepal 관련 변수들 + Speicies변수만 추출하라
            iris %>%
            	filter(Species=="setosa") %>%
            	select(Sepal.Length, Sepal.Width, Species)
            ```
            
        
        **Preprocessing: 변수 전처리하기**
        
        - Base syntax in R
            
            데이터는 `palmerpenguins`패키지 내장 데이터인 `penguins` 데이터를 사용하겠습니다. 
            
            **(1) 결측치 처리** 
            
            ```r
            library(palmerpenguins)
            data("penguins")
            summary(penguins) 
            
            # 먼저 base R syntax 를 사용해서 결측치 처리를 해봅니다. 
            # 어디에 결측치가 있을까? 확인 
            colSums(is.na(penguins)) # column 별로 sum 계산 
            penguins[which(is.na(penguins$bill_depth_mm)),] # 구체적으로 확인해보자 
            penguins[which(is.na(penguins$sex)),]
            
            # sex 변수에서 결측치를 가진 케이스를 모두 제거하고 새로운 데이터로 저장해 봅니다. 
            penguins_new = penguins[-which(is.na(penguins$sex)),]
            summary(penguins_new) # 확인 
            
            # 더 쉬운 방법: na.omit()
            na.omit(penguins) 
            
            # 참고) 새로운 데이터로 저장해주셔야 업데이트 됩니다.  
            ```
            
            **(2) 새 변수 만들기** 
            
            펭귄들의 부리(bill)의 length와 depth를 곱해서 면적(area) 변수를 새로 만들어 봅시다. 
            
            ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%2010.png)
            
            ```r
            # Base R syntax: 
            penguins_new$bill_area_mm <- penguins_new$bill_depth_mm * penguins_new$bill_length_mm
            ```
            
            펭귄들의 body mass는 현재 gram 단위로 되어 있습니다. 이를 kg 단위로 바꿔 새로운 변수로 저장해 주세요. 
            
            ```r
            # Base R syntax: 
            penguins_new$body_mass_kg <- (penguins_new$body_mass_g)/1000
            ```
            
            **(3) 변수 범주화(categorizing; grouping)**
            
            연속형 변수를 범주화해봅시다. 펭귄들의 body_mass_kg 변수의 분포를 살펴보세요. 중위값 이하의 경우 0의 값을, 중위값 초과의 경우 1의 값을 갖는 이항 변수로 범주화해주세요. 
            
            ```r
            # 분포 확인 
            summary(penguins_new$body_mass_kg) 
            quantile(penguins_new$body_mass_kg) 
            
            # recoding 
            penguins_new$body_mass_kg[penguins_new$body_mass_kg <= 4.050] = "중위값 이하"
            penguins_new$body_mass_kg[penguins_new$body_mass_kg > 4.050] = "중위값 초과"
            
            # check 
            table(penguins_new$body_mass_kg)
            ```
            
            이런 방식의 재부호화는 기존 변수 위에다 특정 조건에 부합하는 경우에만 특정 값을 덮어쓴다는 점에서 추천드리지 않습니다. 항상 전처리를 하실 때에는 원래 변수를 그래도 놔둔 채로 새로운 변수를 만들어 사용하는 편이 좋습니다. 하지만 base 함수를 이용하는 경우, 그 방식이 매우 복잡해 집니다. 일단 빈 깡통(벡터)을 하나 만들어 두고, 이 빈 깡통에 if else 구문을 사용하여 값을 하나씩 채워 넣습니다. 이후 값이 모두 채워진 벡터를 데이터의 새 변수로 붙여 쓰면 됩니다. 코드는 아래와 같습니다. 단, 이 코드를 이해하기 위해선 for 구문(loop), if else 구문 등의 함수 기능을 공부하셔야 하므로 참고만 해주시길 바랍니다. 
            
            ```r
            body_mass_group = c() # 빈 깡통 만들기 
            
            # for 구문 + if else 구문 혼합하여 빈 깡통에 값 채워넣기 
            for(i in 1:nrow(penguins_new)){
              if(penguins_new$body_mass_kg [i] <= 4.050){
                body_mass_group[i] = "중위값 이하"
              }else{
                body_mass_group[i] = "중위값 초과"
              }}
            
            penguins_new$body_mass_group = body_mass_group # 값이 채워진 벡터를 새로운 변수로 할당 
            
            # 확인
            table(penguins_new$body_mass_group) 
            ```
            
        - `Tidyverse`
            
            이제까지 (1) 결측치 처리, (2) 새 변수 만들기, 그리고 (3) 범주화를 R의 base syntax 만으로 해보았습니다. 이렇게 어떤 패키지를 불러오지 않더라도 base 함수만으로도 분석이 가능하긴 합니다만, 더 효율적이고 쉬운 방법이 있습니다. `Tidyverse`를 사용하여 동일한 분석을 한번에 진행해 보겠습니다. 이 패키지의 가장 큰 장점은 `%>%` (pipe operator; `|>` 도 가능)을 통한 연속적이고 효율적인 코딩입니다. `Tidyverse`문법에서는 변수 전처리를 할 때 `mutate()` 를 사용해 줍니다. 또한 ‘빈 깡통을 만들고 → for loop, if else 구문을 조합하여 값을 채워 넣고 → 값을 채운 벡터를 새로운 변수로 할당’하는 과정을 더 단순화해주는 `ifelse()` 함수도 `Tidyverse` 를 사용하는 큰 이유 중 하나입니다.  
            
            ```r
            # Tidyverse 
            penguins %>% # 분석 대상이 되는 데이터 
              drop_na()  %>% # 결측치 처리 
              mutate(bill_area_mm = bill_depth_mm*bill_length_mm, # 부리 면적 변수 생성
                     body_mass_kg = body_mass_g/1000, # 무게 kg 단위로 바꾼 변수 생성 
                     body_mass_group = ifelse(body_mass_kg > median(body_mass_kg), "중위값 초과", "중위값 이하")
            				 ) -> penguins_new_tidy # 새 데이터로 저장 
            
            # 확인
            table(penguins_new_tidy$body_mass_group)
            ```
            
            - **(보너스) tidyverse - group_by()**
            
            `tidyverse`패키지의 `group_by()` 함수를 사용하면 그룹 별로 변수 전처리를 간편하게 할 수 있습니다. `gapminder` 데이터는 국가들이 대륙 그리고 연도 안에 nested 되어 있는 구조라고 할 수 있습니다. 이 데이터를 가지고 그룹 별로 평균을 계산하는 연습을 해봅시다. 
            
            ```r
            # 대륙 별 변수 평균 요약하기: summarise(), mean() 
            gapminder %>%
              group_by(continent) %>% # 대륙 별로 묶어서 
              summarise(  
                lifeExp_mean = mean(lifeExp), # 평균 값들을 요약해라 
                pop_mean = mean(pop), 
                gdpPercap_mean = mean(gdpPercap)
              )
            
            # 연도 별  
            gapminder %>%
              group_by(year) %>% # 연도 별로 묶어서 
              summarise( 
                lifeExp_mean = mean(lifeExp), # 평균 값들을 요약해라 
                pop_mean = mean(pop), 
                gdpPercap_mean = mean(gdpPercap)
              )
            
            # 대륙 X 연도 별 변수 평균 구한 변수를 새로운 변수로 추가하기: mutate() 
            gapminder %>%
              group_by(continent, year) %>% 
              mutate( 
                lifeExp_mean = mean(lifeExp),  
                pop_mean = mean(pop), 
                gdpPercap_mean = mean(gdpPercap)
              ) -> test
            
            # 확인 
            glimpse(test)
            ```
            

---

1. 데이터 시각화 **Visualizastion in R**
    - 4-1. R 기본 그래프 ***R base plot***
        
        먼저 R에서 기본으로 제공하는 base 함수들로 시각화 연습을 해본 후, `tidyverse`의 `ggplot2()` 를 통해 시각화하는 연습을 해보겠습니다. 
        
        Base 함수들 중 자주 쓰는 것들은 다음과 같습니다: `plot()`, `hist()`, `barplot()`그리고 `boxplot()`. 이 함수들을 사용하여 `gapminder` 데이터를 다양하게 시각화해 봅시다. 
        
        ```r
        # plot() : 변수들 간 관계를 한 눈에 볼 수 있는 이변량 그래프 그리기 (산점도; scatterplot) 
        plot(gapminder)
        ```
        
        ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%2011.png)
        
        예) 기대수명이 증가할수록 인구는 어떻게 변화할까요? x축은 lifeExp, y축은 pop의 값들을 산점도로 그려 표현한 것이 바로 5행 4열에 있는 그래프입니다. 패턴을 보니 lifeExp 변수와 pop 변수 간 양의 상관관계가 있습니다. 즉 기대수명이 높아질수록 인구는 증가하는 추세를 보입니다. 
        
        이 두 변수 간 그래프를 확대해 볼까요? `plot(x축, y축)` 
        
        ```r
        plot(gapminder$lifeExp, gapminder$pop) 
        
        # options 추가 
        plot(gapminder$lifeExp, gapminder$pop, col=gapminder$country, pch=19, 
             xlab="Life Expectancy", ylab="Population", 
        		 main="Relationship between life expectancy and population")
        ```
        
        ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%2012.png)
        
        연속형 변수의 빈도 분포를 살펴보는 데에는 `hist()` 함수를 사용합니다. 기대수명 변수의 히스토그램을 그려봅시다. 
        
        ```r
        hist(gapminder$lifeExp)
        
        # customize 
        colors() # check available colors in R 
        hist(gapminder$lifeExp, col="whitesmoke", 
        		 xlab="Life Expectancy", main="Histogram of Life Expectancy")
        abline(v=mean(gapminder$lifeExp), col="wheat4", lty=2, lwd=2) # add line
        ```
        
        ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%2013.png)
        
        다음은 범주형 변수의 분포를 살펴보기에 좋은 `barplot()` 입니다. 각 대륙에 해당하는 값들이 몇 번 등장하는지를 시각화해봅시다. 
        
        ```r
        table(gapminder$continent) # 빈도표 
        
        # 빈도표 자체를 input으로 넣어서 barplot 그리기
        barplot(table(gapminder$continent)) 
        
        barplot(table(gapminder$continent), 
                col = c("lightblue", "mistyrose",
                        "lightcyan", "lavender", "whitesmoke"),
                main = "Barplot")
        ```
        
        ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%2014.png)
        
        마지막으로 범주형 변수 별로 연속형 변수의 분포를 살펴보기에 좋은 `boxplot()` 입니다. 각 대륙 별로 기대수명의 분포를 시각화해봅시다. 
        
        ```r
        boxplot(lifeExp ~ continent , data = gapminder) 
        
        boxplot(lifeExp ~ continent , data = gapminder,
                col = c("lightblue", "mistyrose",
                        "lightcyan", "lavender", "whitesmoke"),
                main = 'Boxplot',
                xlab = "Continent", 
                ylab = "Life Expectancy")
        ```
        
        ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%2015.png)
        
    - 4-2. `**Tidyverse - ggplot2**`
        
        다음은 `tidyverse`의 `ggplot2` 를 통한 시각화를 연습해 보겠습니다. `ggplot2`의 “*GG”는 Gramar of Graphics* 를 의미합니다. `%>%` (파이프 연산자)를 통해 층을 겹겹이 쌓아올려 효율적인 시각화가 가능하며, 여러가지 테마를 적용하여 customize할 수 있다는 점이 장점입니다 (반대로 말하면, 자유도가 높다는 게 처음 배울 때 진입장벽으로 작용할 수 있습니다). 하나씩 천천히 해봅시다! 
        
        기본적인 문법 구조는 다음과 같습니다: 
        
        ```r
        데이터 %>% 
        		ggplot(aes(x=x축에 올 변수 이름, y=y축에 올 변수 이름)) + # aesthetic - coordination space 그리기 
        		geom_point() + # geometry - geom_으로 시작하는 함수 입력 
        		theme() # theme 적용 - 꾸미기
        ```
        
        `ggplot()` 함수를 통해 축을 설정하고 좌표 공간을 먼저 만들어 주신 후에는 파이프 연산자가 아닌 `+`로 연결을 해주세요. 
        
        ```r
        # scatterplot
        # basic form: 
        gapminder %>% 
          ggplot(aes(x=lifeExp, y=pop)) + 
          geom_point()
        
        # color by continent: 
        gapminder %>% 
          ggplot(aes(x=lifeExp, y=pop, col=continent)) + 
          geom_point()
        ```
        
        ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%2016.png)
        
        ```r
        # theme: 
        # 아래의 패키지를 설치해 주시고, 불러와 주세요:
        install.packages("ggthemes")
        install.packages("ggpubr")
        library(ggthemes)
        library(ggpubr) 
        
        gapminder %>% 
          ggplot(aes(x=lifeExp, y=pop, col=continent)) + 
          geom_point() +
          theme_pander() + # 테마 설정 
        	xlab("Life Expectancy") + # x축 라벨
        	ylab("Population")  # y축 라벨
        
        gapminder %>% 
          ggplot(aes(x=lifeExp, y=pop, col=continent)) + 
          geom_point() +
          theme_pander() + 
          xlab("Life Expectancy") +
          ylab("Population") +
          ggtitle("Relationship between life expectancy and population") + # 그래프 제목 
          theme(legend.position = "bottom") + # 범례 위치 
          scale_color_wsj() # 색상 테마 적용 
        ```
        
        ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%2017.png)
        
        대륙별로 따로 그리고 싶다면: `facet_grid()` 함수를 추가. (자매품: `facet_wrap()` 도 있음) 
        
        ```r
        gapminder %>% 
          ggplot(aes(x=lifeExp, y=pop, col=continent)) + 
          geom_point() +
          theme_pander() + 
          xlab("Life Expectancy") +
          ylab("Population") +
          ggtitle("Relationship between life expectancy and population") + 
          theme(legend.position = "none") +  # 범례 삭제 
          scale_color_wsj() +
          facet_grid(~continent) # 대륙 별로 따로 grid를 설정 
        ```
        
        ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%2018.png)
        
        다음은 기대수명 변수의 히스토그램을 그려봅시다. 
        
        ```r
        gapminder %>% 
          ggplot(aes(x=lifeExp)) + 
          geom_histogram() +
          theme_pander()
          xlab("Life Expectancy")
        ```
        
        ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%2019.png)
        
        바 그래프를 그려 봅시다. 대륙 별로 gdpPercap 변수의 평균을 계산하여 gdppc 변수를 새로 만들어 주신 후, x축에는 대륙, y축에는 gdppc 평균 값이 오도록 축을 설정해 주세요. 이번에는 Stata 테마를 적용해 보겠습니다. 
        
        ```r
        gapminder %>%
          group_by(continent) %>% # continent 별로 
          summarise( 
            gdppc = mean(gdpPercap) # gdpPercap 변수의 평균 값을 취해 gdppc 변수에 넣어라 
          ) %>%  # 이 데이터를 기반으로 ggplot을 그리자 
          ggplot(aes(x=continent, y=gdppc, fill=continent)) + # 좌표 설정 
          geom_col() + # 바 그래프 그려 넣을 것임을 알려주고, 
          theme_stata() + # 테마 설정 
          scale_fill_stata() # 대륙 별로 색상을 채워 넣을 때 색상 테마 또한 설정 
        ```
        
        ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%2020.png)
        
        마지막으로 각 대륙 별로 기대수명의 분포를 박스플롯으로 시각화해봅시다. 테마는 미니멀 테마로 설정하고, 범례는 제거해 줍시다. 
        
        ```r
        gapminder %>%
          ggplot(aes(x=continent, y=lifeExp, fill=continent)) + 
          geom_boxplot() +
          theme_minimal() +
          theme(legend.position = "none"))
        ```
        
        ![Untitled](Introduction%20to%20R%20ee13128818d44582beb7844bfec6d5e1/Untitled%2021.png)
        

---

1. 나가며 **Further Tips**
    - 유용한 소스들 ***Useful open sources***
        
        [Welcome | R for Data Science](https://r4ds.had.co.nz/index.html)
        
        [R Graphics Cookbook, 2nd edition](https://r-graphics.org/)
        
        [Welcome | ggplot2](https://ggplot2-book.org/index.html)
